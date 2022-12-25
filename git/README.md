# Git

## Как загружать документы на GitHub (How to upload files to Github)

Надо нажать на паутинку, затем откроется список. Нажать на тот файл, кщторый хочешь
сделать комит, проверить какие изменения внесены в файл, затем нажать на +. После
этого написать вверху коротко какие изменения были внесены и нажать на галочку
комит. После этого, выбрать команду Push. Затем проверить на Github все ли правильно
загрузилось.


## My Git flow

- State is `master` and `develop` are on the same commit in local and remote
- Switch to `develop`

    ```
    git switch develop
    ```

- Do changes in `develop`

    ```
    git add -i
    git commit -m "Comment on your changes"
    ```

- Rebase `develop` on the top of `master`

    ```
    git rebase master
    ```

- Push `develop` to remote

    ```
    git push --force
    ```

- GitHub: Create a Pull Request `develop` > `master`
- GitHub: Merge the Pull Request by "Rebase and Merge"
- Switch to `master` and pull changes

    ```
    git switch master
    git pull
    ```

- Switch to `develop` and rebase `develop` on the top of `master`

    ```
    git switch develop
    git rebase master
    ```
