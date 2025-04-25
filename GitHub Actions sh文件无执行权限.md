相关sh文件未授予执行权限

win
git update-index --chmod=+x  xxx.sh  赋予单个文件权限
Get-ChildItem -Path "D:\github\xxx" -Recurse -Filter *.sh | ForEach-Object {
    git update-index --chmod=+x $_.FullName
}    批量赋予文件夹下所有sh文件权限

出现的 LF will be replaced by CRLF 警告是 Git 的换行符自动转换提示，不影响权限修改。若需禁用此功能：
git config core.autocrlf false

git ls-files --stage | Select-String "\.sh$"  查询文件执行权限  100755 e69de29... 0 build.sh  # 100755 表示可执行权限

git commit -m "chore: 为所有 .sh 文件添加执行权限"
git push

