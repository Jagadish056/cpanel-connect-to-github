# cPanel Connect To GitHub

1. Create a Git Repository as public visibility.
2. Push your entire website code to your Git Repository.
3. Open cPanel
   - Go to Git<sup>TM</sup> Version Control
   - Click on New button
   - Enter your Git Repository Clone URL
   - Click on Create button
4. Before deploying your code to cPanel, you must have `.cpanel.yml` file on your source code.
5. In `.cpanel.yml` file

- Go to [The deployment YAML file](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-deployment/#deploy-individual-files)

```
---
deployment:
  tasks:
    - export DEPLOYPATH=/home/user/public_html/subfolder
    - /bin/cp * $DEPLOYPATH
```

- `DEPLOYPATH=/home/user/public_html/subfolder` - Your website full path and replace `user` with your cpanel `username`.
- `/bin/cp * ` - '\*' means all file deploy in cPanel

6. Again, push the source code of your website to the Git Repository.
7. In Git Version Control
   - Click on `Manage` button, from the list
   - Click on `Update` button in Basic Information tab
   - Click on `Update from Remote` & `Deploy Head Commit` button in Pull or Deploy tab
8. Finally, Check your website url.
