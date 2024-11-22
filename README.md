# python-docs
Easy deployable python project documentation.

# Steps
1. Create virtual environment
2. Install dependencies
3. Run `mkdocs new .`
4. Set theme in `mkdocs.yml`
5. Configure

# Azure
1. Go to Azure Static Web Apps
2. Click create
3. Choose your subscription & resource group
4. Give a name
5. Choose your hosting plan (Free is an option)
6. Set GitHub as source and login
7. Select your project
8. At the build presets, choose custom
9. Leave the app location intact as root ("/"), the Api location blank and set the the Output location to "site"
10. Choose "Deployment Token" at the deployment configuration
11. Select your region
12. Deploy the app
13. Add the following code block within the Checkout and Build & Deploy steps within your workflow:
```yml
      - uses: actions/setup-python@v5
        with:
          python-version: '3.12'
      - run: pip install -r requirements.txt
      - run: mkdocs build
```