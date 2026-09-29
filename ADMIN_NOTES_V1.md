## Reset Roadmap Password

The Dockerized version of Rough Track is a prototype, so password locking for editing is implemented with simplicity in mind. If a user forgets their roadmap’s password, the only way to reset it is by sending an API request to the web server using the administrator password configured in the `.env` file at server startup.

```bash
curl -X POST localhost:8080/api/v1/admin/resetRoadmapPassword \
    -H "Content-Type: application/json" \
    -d '{"roadmapId": "4", "newPassword": "test", "adminPassword": "test"}'
```

**Notes**:

- Replace "your-admin-password" with the actual admin password set in your .env.
- This request will update the roadmap’s password and return the roadmap metadata (ID, title, created/updated timestamps).
- Ensure the server is running and the endpoint is accessible over the network.
