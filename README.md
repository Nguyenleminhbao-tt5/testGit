### Khái niệm của Git

- Repo: local vs remote 

- Branch: local vs remote 

- Commit


### Commands

#### Clone repo

- Generate ssh key: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

- Add public key: https://github.com/settings/keys

- Clone repo: git clone [git-url] 

#### Working on branch

- View branches and current branch: git branch 

- Create new branch: git checkout -b [branch name]

- Push code:

    + `git add [files]` or `git add .`

    + git commit -m "[your message]"

    + git push [remote name] [local branch]:[remote branch]

        + git push: push to upstream

        + git push github: push to remote branch on remote github

        + git push github feature2

        + git push github feature1:feature2 => ko khuyến khích 

        + git push github :feature1 => delete remote feature1

- Pull code:

    - git pull 

    - `git fetch` -> `git merge [branch name]` or `git rebase [branch name]` 

        + git rebase: sử  dụng trên nhánh private (làm 1 mình). Không sử dụng trên nhánh làm chung or nhánh làm một mình bà rebase báo conflict 2 lần.

- Resolve conflict:
    - Lựa chọn:

            - Bỏ code mình (1)

            - Bỏ code người ta (2)

            - Giữ cả 2 (có thể modify) (3)

        => Đọc code tự tin thì chọn (1) or (2) or (3). Ko tự tin thì kiếm người tạo ra commit conflict với mình để discuss và giải quyết. 

    - Giải quyết:

        - Sửa file(s) bị conflict     

        - git add [file(s)]

        - git commit -m "[message]"

        - git push 

#### Common commands

- `git stash`: tạm thời bỏ những thay đổi để chuyển nhánh. Khi lấy lại thay đổi dùng `git stash apply`

- `git pull` = `git fetch` + `git merge`

- git checkout:

    - Chuyển nhánh: `git check [tên nhánh]`

    - Chuyển version file: `git check [commit id] [tên file]`

    - Tạo nhánh mới: `git check -b [tên nhánh]`

- git status: provide info: current branch, file untracked, file modify, file ready to commit, conflict.

- git reset:

    - mix (default): bỏ lịch sử, giữ code, ko add changes vào index 

    - soft: bỏ lịch sử, giữ code 

    - hard: bỏ code, bỏ lịch sử 

- git config 

    + git config --local user.name [name]

    + git config --global user.email [email]

#### GUI tool

- Git cola: 
    
    + view status of branch + support full commands (commit, push, pull...)

    + review change trước khi commit

    + commit 1 phần file hay revert change dễ dàng

- gitk: view history 


#### Configure multiple sss keys

- Generate keys

- Add public keys to github accounts

- config file ~/.ssh/config:

    ```
    Host github-nhannm.com => alias, đặt tùy thích, đặt gì thì khi clone code phải sử dụng như vậy 
        HostName github.com => domain thật sự của git server sử dụng 
        User git => mặc định, ko chỉnh sửa 
        IdentityFile ~/.ssh/nhannm/id_rsa => file private key pair với public key đã đăng ký
    ```




#### Note

- Create branch : git checkout -b [ten nhanh]
- Switch branch : git checkout [ten branch]
- Delete branch : git branch -d [ten nhanh]
- View remote name: git remote -v
- Delete remote branch: git push [remote name] :[branch delete]

