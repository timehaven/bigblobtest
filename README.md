# bigblobtest

```
#
# On github: make this new empty repo, then:
#

mkdir ~/bigblobtest
cd ~/bigblobtest

echo "# bigblobtest" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:timehaven/bigblobtest.git
git push -u origin main

du -csh ../bigblobtest
112K    ../bigblobtest
112K    total

git checkout -b bigblobbranch
mv ~/Downloads/mini.iso ~/Downloads/netboot.tar .

ls -lh 
total 179472
-rw-r--r--  1 ryan  staff    14B Nov  5 09:41 README.md
-rw-r--r--  1 ryan  staff    48M Nov  5 09:45 mini.iso
-rw-r--r--  1 ryan  staff    40M Nov  5 09:45 netboot.tar

git add *
git commit -m "Add bigfiles"
git push -u origin bigblobbranch
cd ..

du -csh bigblobtest
160M    bigblobtest
160M    total

rm -fr bigblobtest
git clone git@github.com:timehaven/bigblobtest.git

du -csh bigblobtest
 37M    bigblobtest
 37M    total

cd bigblobtest
git fetch origin bigblobbranch
git checkout bigblobbranch

ls -lh
total 179472
-rw-r--r--  1 ryan  staff    14B Nov  5 09:41 README.md
-rw-r--r--  1 ryan  staff    48M Nov  5 09:45 mini.iso
-rw-r--r--  1 ryan  staff    40M Nov  5 09:45 netboot.tar

du -csh ../bigblobtest
124M    bigblobtest
124M    total

#
# On github:  delete branch in UI
# (Could be done via command line if you want.)
#

# blobs are still in local .git

git checkout main
git branch -D bigblobbranch. # use -d if already merged

du -csh ../bigblobtest
 73M    ../bigblobtest
 73M    total
(base) ➜  bigblobtest git:(main) git branch
* main

# clean local blobs
# (apparently this could have side effects for large repos like ours)
# https://stackoverflow.com/a/2116892
git reflog expire --all --expire=now
git gc --prune=now --aggressive

du -csh ../bigblobtest
108K    ../bigblobtest
108K    total

cd ..
rm -fr bigblobtest
git clone git@github.com:timehaven/bigblobtest.git

du -csh bigblobtest
108K    bigblobtest
108K    total

cd bigblobtest

git branch -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```
