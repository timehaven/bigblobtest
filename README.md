# bigblobtest

```
# make this new empty repo, then:

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

cd ..
du -csh bigblobtest
124M    bigblobtest
124M    total

# delete branch on github

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