# mdbook
## 安裝mdbook
```
> cargo install mdbook --force
```
## 建立mdbook
```
> mdbook init my-first-book
```
```
Do you want a .gitignore to be created? (y/n)
> y
What title would you like to give the book?
> my first book
```
```
cd my-first-book
mdbook serve --open
```
```
git init -q
git add .
git commit -m 'first commit'
git clean -dfx
```