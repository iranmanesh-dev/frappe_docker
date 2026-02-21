# ERPNext Coolify Deployment – Important Post-Deploy Commands

These commands are run **inside the `backend` container** via Coolify's Terminal tab.

**Important notes:**
- All commands use the site name `crm.floriaweb.com`
- Run them after initial site creation or after major redeploys / config changes
- Use the same password you set during `bench new-site`

## Core Configuration Commands (run these after every fresh deploy if needed)

```bash
# 1. Set the correct host_name (prevents "localhost does not exist" 404)
bench --site crm.floriaweb.com set-config host_name https://crm.floriaweb.com

# 2. Enable background jobs / scheduler (important for emails, recurring tasks, etc.)
bench --site crm.floriaweb.com enable-scheduler

# 3. Clear cache (always good after config changes)
bench --site crm.floriaweb.com clear-cache

# 4. Restart all processes (gunicorn, workers, etc.)
bench restart
