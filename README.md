# Git�ٲ��ֲ�
------
## �����汾��
git init

## ���ļ��޸���ӵ��ݴ���
git add test.txt test2.txt

## ���ݴ��������������ύ����ǰ��֧��
git commit -m '����������ļ�'

## �޸��ļ��󣬲鿴״̬
git status

## �鿴�����޸���ʲô����(֮�󣬾Ϳ��Է��ĵ�add��commit��)
git diff test2.txt

## �鿴�޸��ύ��¼
git log --pretty=oneline

## �汾���ˣ�git commit����Ҫ������
####����ǰ�汾HEAD����һ���汾����HEAD^������һ���汾����HEAD^^,Ҳ���Լ��ϰ汾�ţ�
git reset --hard HEAD^
git reset --hard commit_id

## Ҫ�ط�δ������git reflog�鿴������ʷ���Ա�ȷ��Ҫ�ص�δ�����ĸ��汾��
git reflog

## �����޸�
#### ���԰��ݴ������޸ĳ�������unstage�������·Żع�������(git add����Ҫ����)
git reset HEAD test.txt
#### ���Զ������������޸�
git checkout -- test.txt

## ɾ���ļ����ڹ�����ɾ����һ���ļ���
#### �Ӱ汾����ɾ�����ļ����Ǿ�������git rmɾ��������git commit��
git rm test.txt
git commit -m "remove test.txt"
#### ɾ���˹��������ļ����汾���ﻹ�У�����Ҫ����ɾ���ļ��ָ������°汾��
git checkout -- test.txt

## ����SSH key
ssh-keygen -t rsa -C "youremail@example.com"

## �������ؿ��githubԶ�ֿ̲�
git remote add origin git@github.com:example/learngit.git

## �ѱ��ؿ�������������͵�Զ�̿���(��һ�����ͣ�������-u����)
git push -u origin master

## ��ÿһ���ύ�����͵�Զ�̿���
git push origin master

## �ȴ���Զ�̿⣬Ȼ�󣬴�Զ�̿��¡��
git clone git@github.com:example/test.git

## ������֧
git branch dev         ������֧dev
git branch             �г����з�֧����ǰ��֧ǰ����һ��*��
git checkout dev       �л���dev��֧
git checkout -b dev    �������л���dev��֧

## �ϲ���֧
#### ��dev��֧�ϣ��޸��˴��룬����commit��֮����Ҫ�ϲ���master��֧
git checkout master
git merge dev          �ϲ�ָ����֧����ǰ��֧
git branch -d dev      �ϲ���ɺ󣬾Ϳ��Է��ĵ�ɾ��dev��֧��

## ��������֧����ͬһ�ļ������޸ģ��ϲ���֧ʱ�ͻ������ͻ����Ҫ���뵽�ļ��޸ĳ�ͻ���֣��ٴ�add&&commit
## ʹ����������鿴��֧�ĺϲ����
git log --graph --pretty=oneline --abbrev-commit

## �ϲ���֧ʱ��ǿ�ƽ���Fast forwardģʽ
#### Git�ͻ���mergeʱ����һ���µ�commit���������ӷ�֧��ʷ�ϾͿ��Կ�����֧��Ϣ
git merge --no-ff -m "merge with no-ff" dev

## ��ʱBug��֧

```
# Git���ṩ��һ��stash���ܣ����԰ѵ�ǰ�����ֳ������ء����������Ժ�ָ��ֳ����������
git stash
# ����ȷ��Ҫ���ĸ���֧���޸�bug���ٶ���Ҫ��master��֧���޸����ʹ�master������ʱ��֧
git checkout master
git checkout -b issue-101
# �޸���ɺ��ύ
git add readme.txt
git commit -m "fix bug 101"
# �л���master��֧
git checkout master
git merge --no-ff -m "merged bug fix 101" issue-101
git branch -d issue-101
# �л���dev��֧������δ��ɵĹ���
git checkout dev
# �鿴֮ǰ�Ĺ����ֳ�
git stash list
# �ָ������ֳ���ͬʱ��stash����Ҳɾ�ˣ�git stash apply����ɾ��stash���ݣ�
git stash pop

## ���stash���ָ���ʱ������git stash list�鿴��Ȼ��ָ�ָ����stash�������
git stash apply stash@{0}
```

## �鿴Զ�̿����Ϣ��-v ��ϸ��Ϣ��
git remote
git remote -v

## ���ͷ�֧(�Ѹ÷�֧�ϵ����б����ύ���͵�Զ�̿�)
git push origin dev   origin Զ�̿⣻dev Ҫ���͵ı��ط�֧

## ����Զ��origin��dev��֧������
```
    git checkout -b dev origin/dev
    # ��dev�ϼ����޸ģ�Ȼ��ʱ��ʱ�ذ�dev��֧push��Զ�̣�
    git commit -m "xxxxxx"
    git push origin dev
    # ������ͬʱ��dev�ϵ��ļ��������޸ģ�commit��,push�ͻ���ֳ�ͻ����ʱ��Ӧ��ʹ��git pull�����µ��ύ��origin/devץ����

    git pull
    # ���ʹ��git pullҲʧ���ˣ�ԭ����û��ָ������dev��֧��Զ��origin/dev��֧�����ӣ�������ʾ������dev��origin/dev������,��pull
    git branch --set-upstream dev origin/dev
    git pull
    # ����г�ͻ��Ҫ�ȴ����ͻ,��push
    git push origin dev

```

## ������ǩ
 git tag v1.0



