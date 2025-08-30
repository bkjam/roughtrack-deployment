## Rough Track

RoughTrack is a prototype for creating **Now-Next-Later roadmaps** helping teams prioritize tasks and communicate priorities effectively with stakeholders.

## Support

If you encounter any issues or have questions about RoughTrack, you can create an issue on our GitHub repository. When submitting an issue, please provide a clear description of the problem, steps to reproduce it, and any relevant screenshots or error messages.

Since RoughTrack is a prototype, we may not be able to respond immediately, but your report will help us improve the project for future versions.

## Tech Stack

RoughTrack consists of the following components:

1. Frontend (React.js)
   - UI & Components: [tailwindcss (styling)](https://tailwindcss.com/) & [lucide-react (icons)](https://lucide.dev/guide/packages/lucide-react) & [react-color (color picker)](https://casesandberg.github.io/react-color/) & [react-markdown](https://github.com/remarkjs/react-markdown) & [react-hot-toast (notifications)](https://react-hot-toast.com/) & [ag-grid-react (data grids)](https://www.ag-grid.com/)
   - Data & Forms: [axios (http client)](https://axios-http.com/docs/intro) & [react-hook-form (form library)](https://react-hook-form.com/) & [@tanstack/react-query v5 (data fetch & cache)](https://tanstack.com/query/latest)
   - Drag & Drop: [@dnd-kit](https://dndkit.com/)
   - Routing: [react-router v7 (routing library)](https://reactrouter.com/)
   - State Management: [zustand](https://zustand.docs.pmnd.rs/getting-started/introduction)
   - Utils: [date-fns (date utility library)](https://date-fns.org/)
2. Backend (Fastify)
   - Web Framework: [fastify)](https://fastify.dev/)
   - Datebase Integration: [prisma (ORM toolkit)](https://www.prisma.io/)
3. Database
   - [Postgresql](https://www.postgresql.org/)

## Self Hosting

> Note that for the `DATABASE_URL`, database name must be **mydb** and schema must be **public**

### Docker Compose

Using the sample [docker-compose.yml](./docker-compose.yml) file, run the command `docker compose -f docker-compose.yml up -d`

### Helm Chart

To be updated....
