# phpmyadmin Troubleshooting

- ## Fix Count Error on Data Tables

  - Edit sql.lib.php

```shell
nano /usr/share/phpmyadmin/libraries/sql.lib.php
```
  - Search for the following text using `Ctrl + w`
    - `((empty($analyzed_sql_results['select_expr'])) || (count($analyzed_sql_results['select_expr'] == 1) && ($analyzed_sql_results['select_expr'][0] == ‘*’)))`
  - Replace with the following
    - `((empty($analyzed_sql_results['select_expr'])) || (count($analyzed_sql_results['select_expr']) == 1) && ($analyzed_sql_results['select_expr'][0] == ‘*’))`
  - Write out `Ctrl + o`
  - Exit `Ctrl + x`