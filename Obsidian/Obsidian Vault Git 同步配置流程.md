1. 终端确保本地是否安装GitHub CLI 工具 `gh`：brew install gh
2. GitHub 登录认证：（就不需要鉴权了）
```
gh auth login依次选择：
- GitHub.com
- HTTPS
- Login with a web browser
- copy url：https://github.com/login/device
- 浏览器上输入code码即可完成验证
- **tips：**
- gh auth status检查是否登陆
```
![[Pasted image 20250623162914.png]]3. 本地目录为<mark style="background: #D2B3FFA6;">/Users/v_gukangjie/Documents/Obsidian</mark>【不需要重复初始化】
```git
cd /Users/v_gukangjie/Documents/Obsidian
git init
git add .
git commit -m "初始化：添加所有笔记与插件配置"
```
4. GitHub上新建仓库：不要勾选 `README` 或 `.gitignore`
5. 关联远程仓库并推送：
```
git remote add origin https://github.com/用户名/仓库名.git
git branch -M main
git push -u origin main
```
![[Pasted image 20250623164827.png]]6. 后续同步命令（更新笔记）
```git
git add .
git commit -m "update notes"
git pull --rebase
git push
```
7. 远程计算机如何使用：
- 同样安装好 Git + GitHub CLI
- 登录 GitHub 账号：gh auth login
- 克隆仓库：git clone https://github.com/用户名/仓库名.git