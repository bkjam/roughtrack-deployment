## Choosing AUTH_MODE

> [!WARNING]
> **Choose `AUTH_MODE` (`oidc` or `trusted-header`) once, at initial deployment, and avoid changing it later on a deployment with real
> data.**

User accounts are keyed on the identifier your auth mechanism hands RoughTrack: the OIDC subject, or the `X-User-Id` header in
trusted-header mode. RoughTrack assumes, but does not verify, that this identifier stays the same for a given person if you ever switch
modes. For example, a trusted-header proxy might forward the same subject it got from OIDC.

If that assumption doesn't hold for your setup, switching modes on an existing deployment risks two different people colliding onto the
same account. If you're not certain the two line up, deploy fresh (a new database) under the new mode instead of switching an existing one
in place.

## Admin access

Admin features (including Backup & Restore) are available to users with the `admin` role:

- **OIDC mode:** set `OIDC_ADMIN_ROLE_CLAIM` to the role name your identity provider issues to admins.
- **Trusted-header mode:** include `admin` in the `X-User-Role` header (comma-separated if there are several roles).

## Backup & Restore (migrating to a new database)

Admins can export all RoughTrack data and load it into a new instance. In the app, click your initials avatar at the top-right of the
navbar and choose **Backup & Restore**.

**Backup** downloads one JSON file containing every user, roadmap, category, task, subtask and roadmap membership. MCP tokens and login
sessions are **not** included. After a migration, users sign in again and generate new MCP tokens.

**Restore** loads a backup file into the current instance:

- It only works on a **fresh, empty database** (no roadmaps, categories or tasks yet). It never merges into existing data.
- Roadmap and task IDs are kept, so existing links keep working.
- Users are matched by the identifier your auth mechanism provides (see [Choosing AUTH_MODE](#choosing-auth_mode)). Restore under the same
  auth setup so accounts line up.
- It's all-or-nothing: if anything fails, the database is left untouched.

### Migration steps

1. On the old instance, open **Backup & Restore** and click **Download backup**.
2. Deploy the new instance against an empty database, using the same `AUTH_MODE` and identity provider.
3. Sign in to the new instance as an admin.
4. Open **Backup & Restore**, choose the backup file, and click **Restore**.
5. Ask users to generate new MCP tokens if they use them.

I added the "Admin access" section, which wasn't in the old in-app text. It's the OIDC_ADMIN_ROLE_CLAIM / X-User-Role explanation I took
off the docs page, and it fits the deployment repo. Drop it if the repo already covers admin setup.
