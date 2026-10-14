# MinIO Deployment Documentation

## Docker Command Used

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  quay.io/minio/minio server /data --console-address ":9001"
```

## Access Details

- **Web Console Port:** 9001 (accessed via KillerCoda's Traffic/Ports panel, forwarded to the browser)
- **API Port:** 9000 (used by S3-compatible clients/SDKs to read and write objects programmatically)
- **Bucket Created:** `client-photos`

## Explanation of Environment Variables (`-e` flags)

The `-e` flag passes environment variables into the running container, which MinIO reads on startup to configure itself:

- `MINIO_ROOT_USER=cloudadmin` — Sets the root/admin username used to log into the MinIO Web Console and to authenticate API requests. This replaces MinIO's default credentials with a custom login.
- `MINIO_ROOT_PASSWORD=CloudNova2026!` — Sets the root/admin password paired with the username above. Together, these two variables secure the server so it isn't left with default, publicly known credentials.

Without these variables, MinIO would fall back to its default `minioadmin` / `minioadmin` credentials, which is insecure for anything beyond quick local testing.

## Verification

Running `docker ps` confirms the `minio-server` container is up, with ports `9000` and `9001` mapped from the container to the host. Running `docker logs --tail 8 minio-server` confirms the server started successfully and is serving the API on port 9000 and the WebUI on port 9001.
