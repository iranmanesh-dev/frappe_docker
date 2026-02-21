in the terminal -> backend 
# in backend container
bench --site crm.floriaweb.com set-config host_name https://crm.floriaweb.com
bench --site crm.floriaweb.com enable-scheduler
bench --site crm.floriaweb.com clear-cache
bench restart
