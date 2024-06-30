# Основы работы с Git

## правим .gitconfig
```
git config --global user.name 'Victor G. Krivulets'
```
```
git config --global user.email victor.krivulets@yandex.ru
```
### создаем папку для локального репозитория
```
mkdir second-project
```
### чтобы инициировать Git, заходим в папку с репозиторием и выполняем
```
git init
```
### добавляем файл в репозиторий
```
git add имя_файла
```
### добавляем все файлы в репозиторий
```
git add --all
```
```
git add .
```
### добавляем файл в репозиторий
```
git commit -m 'changed README.md'
```
### добавляем удаленный репозиторий
```
git remote add origin git@github.com:kvg20051/second-project.git
```
### синхронизация локального репозитория с удаленным (первый пуш):
```
git push -u origin master
```
### далее для всех последующих пушей выполняем
```
git push
```
### посмотреть историю коммитов
```
git log
```
```
git log --oneline
```
### создать новую ветку
```
git branch new_branch
```
### перейти в ветку new_branch
```
git checkout new_branch
```
### удалить ветку new_branch в локально репозитории
```
git push branch -d new_branch
```
### удалить ветку new_branch в удаленном репозитории
```
git push origin --delete new_branch
```



# SSH-keys

### SSH-keys github.com
```
ssh -T git@github.com
```
### SSH-keys gitea
```
???
```
# Mermaid
```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```


To push to GitLab using SSH keys and avoid entering a password, you need to set up SSH keys and configure GitLab to recognize your public key. Here are the steps to do that:

### Step 1: Generate SSH Keys

1. Open your terminal.
2. Generate a new SSH key pair (if you don't have one already) using the following command. Replace `your_email@example.com` with your actual email address.

    ```bash
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```

    You will be prompted to enter a file in which to save the key. Press `Enter` to accept the default location.

    You will also be prompted to enter a passphrase. You can choose to enter a passphrase for added security or leave it empty for convenience.

3. The keys will be generated and stored in the `~/.ssh` directory by default. The public key will be stored in `~/.ssh/id_rsa.pub` and the private key in `~/.ssh/id_rsa`.

### Step 2: Add the SSH Key to the SSH Agent

1. Start the SSH agent in the background.

    ```bash
    eval "$(ssh-agent -s)"
    ```

2. Add your private SSH key to the SSH agent.

    ```bash
    ssh-add ~/.ssh/id_rsa
    ```

### Step 3: Add the SSH Key to Your GitLab Account

1. Copy the contents of your public SSH key to your clipboard. You can use the following command to display the key:

    ```bash
    cat ~/.ssh/id_rsa.pub
    ```

    Then, copy the displayed key.

2. Log in to your GitLab account.
3. Navigate to **User Settings** (usually found by clicking on your profile picture in the top right corner).
4. Click on **SSH Keys** in the left sidebar.
5. Paste your public key into the "Key" field and give it a descriptive title in the "Title" field.
6. Click the **Add key** button.

### Step 4: Configure Git to Use SSH for GitLab

1. Ensure that the Git remote URL is using SSH. You can check this by running:

    ```bash
    git remote -v
    ```

    If the URL starts with `https://`, you need to change it to `ssh://`.

2. To change the remote URL to SSH, use the following command. Replace `your-username` and `your-repo` with your actual GitLab username and repository name.

    ```bash
    git remote set-url origin git@gitlab.com:your-username/your-repo.git
    ```

### Step 5: Test the SSH Connection

1. Test the SSH connection to GitLab to ensure everything is set up correctly.

    ```bash
    ssh -T git@gitlab.com
    ```

    You should see a message like:

    ```plaintext
    Welcome to GitLab, @your-username!
    ```

### Step 6: Push to GitLab

Now, you should be able to push to GitLab without being prompted for a password:

```bash
git push origin main
```

or

```bash
git push origin <your-branch-name>
```

By following these steps, you should be able to push to GitLab using SSH keys without needing to enter a password each time.




## Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

## Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

## Выделение кода
