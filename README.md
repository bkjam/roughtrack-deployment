## Rough Track

RoughTrack is a prototype for creating **Now-Next-Later roadmaps** helping teams prioritize tasks and communicate priorities effectively with stakeholders.

- [Support](#support)
- [Tech Stack](#tech-stack)
- [Image Tag Versions](#image-tag-versions)
- [Self Hosting](#self-hosting)
- [License & Disclaimer](#license--disclaimer)

## Support

If you encounter any issues or have questions about RoughTrack, you can create an issue on our GitHub repository. When submitting an issue, please provide a clear description of the problem, steps to reproduce it, and any relevant screenshots or error messages.

Since RoughTrack is a prototype, we may not be able to respond immediately, but your report will help us improve the project for future versions.

## Overview

### Tech Stack

RoughTrack consists of the following components:

1. Frontend (React.js)
   - UI & Components: [tailwindcss (styling)](https://tailwindcss.com/) & [lucide-react (icons)](https://lucide.dev/guide/packages/lucide-react) & [react-color (color picker)](https://casesandberg.github.io/react-color/) & [react-markdown](https://github.com/remarkjs/react-markdown) & [react-hot-toast (notifications)](https://react-hot-toast.com/) & [ag-grid-react (data grids)](https://www.ag-grid.com/)
   - Data & Forms: [axios (http client)](https://axios-http.com/docs/intro) & [react-hook-form (form library)](https://react-hook-form.com/) & [@tanstack/react-query v5 (data fetch & cache)](https://tanstack.com/query/latest)
   - Drag & Drop: [@dnd-kit](https://dndkit.com/)
   - Routing: [react-router v7 (routing library)](https://reactrouter.com/)
   - State Management: [zustand](https://zustand.docs.pmnd.rs/getting-started/introduction)
   - Utils: [date-fns (date utility library)](https://date-fns.org/)
2. Backend (Fastify)
   - Web Framework: [fastify](https://fastify.dev/)
   - Datebase Integration: [prisma (ORM toolkit)](https://www.prisma.io/)
3. Database
   - [Postgresql](https://www.postgresql.org/)
   - [Sqlite](https://sqlite.org/)

### Image Tag Versions

The currently deployed versions are available on [Docker Hub](https://hub.docker.com/r/bkjam/roughtrack). The main version requires an external PostgreSQL database to be deployed, while the **-lite** version includes a built-in SQLite database inside the Docker container, so no external database setup is needed. All data is stored directly within the container.

| Version        | Variants   | Description         |
| -------------- | ---------- | ------------------- |
| 1.6.0 & latest | 1.6.0-lite | Completed Prototype |

Refer to [CHANGELOG.md](./CHANGELOG.md) for more details on the difference.

## Self Hosting

By default, the main versions comes integrated with **Postgreqsql**, but you can also use the **-lite** version which uses **sqlite**.

### RoughTrack + Postposgql

> Note that for the `DATABASE_URL`, database name must be **mydb** and schema must be **public**

1. using **docker compose**

   Using the sample [docker-compose.yml](./docker-compose.yml) file, run the command:

   ```bash
   docker compose -f docker-compose.yml up -d
   ```

2. using **helm chart**

   To be updated...

### RoughTrack + Sqlite

> Note that for the `DATABASE_URL`, database path must be a **absolute path** with a `file://` prefix.

1. using **docker compose**

   Using the sample [docker-compose-lite.yml](./docker-compose-lite.yml) file, run the command:

   ```bash
   docker compose -f docker-compose-lite.yml up -d
   ```

2. using **helm chart**

   To be updated...

## License & Disclaimer

RoughTrack is a proprietary software prototype. You are free to use and self-host it, but the source code is not open for modification or redistribution.

### Dependencies & Base Images

RoughTrack is built on top of open-source software, including the Node.js Docker image, PostgreSQL, SQLite, and various libraries (React, Fastify, Prisma, etc.). Each dependency is subject to its own license (MIT, Apache 2.0, BSD, or similar). By using RoughTrack, you agree to comply with all applicable licenses of included software.

### Disclaimer

This software is provided “as-is” without warranties of any kind. The developer is not responsible for any data loss, security issues, or other damages arising from the use of RoughTrack, including self-hosted deployments. Use at your own risk.
