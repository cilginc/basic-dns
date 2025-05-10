# Basic Dns Setup
This project is part of [roadmap.sh](https://roadmap.sh/projects/basic-dns) DevOps projects.

---

## Set Up a Github Pages Pages
1. Use your existing Github Pages Project. If you have not completed the GitHub pages project, go ahead and complete that project first.

2. Navigate to your site's repository.

3. Under your repository name, click Settings. If you cannot see the "Settings" tab, select the dropdown menu, then click Settings.

4. In the "Code and automation" section of the sidebar, click Pages.

5. Under "Custom domain", type your custom domain, then click Save. If you are publishing your site from a branch, this will create a commit that adds a CNAME file directly to the root of your source branch. If you are publishing from a custom GitHub Actions workflow, no CNAME file is created, and any existing CNAME file is ignored and is not required.

## Set Up Your Domain

1. Add this IP adresses to your `A` records:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

2. Add this IP adresses to your `AAAA` records:
```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```


## Test Your Domain Records

1. Use `dig` to confirm the dns records:
- For `A` records:
```
dig EXAMPLE.COM +noall +answer -t A
```
You should see results like this:
```
> EXAMPLE.COM    3600    IN A     185.199.108.153
> EXAMPLE.COM    3600    IN A     185.199.109.153
> EXAMPLE.COM    3600    IN A     185.199.110.153
> EXAMPLE.COM    3600    IN A     185.199.111.153
```
- For `AAAA` records:
```
dig EXAMPLE.COM +noall +answer -t AAAA
```
You should see results like this:
```
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8000::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8001::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8002::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8003::153
```
