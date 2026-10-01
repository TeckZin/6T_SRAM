***6T SRAM***
to push to main you need to checkout another branch first push to that branch,
then merge to main

git checkout main
git pull origin main

git checkout -b feature/my-change

# make changes

git add .
git commit -m "Add my change"
git push -u origin feature/my-change
