# Setup — about 5 minutes

1. Replace the placeholders in `README.md`:
   - `YOUR_USERNAME` — your exact GitHub username (appears in five places)
   - `YOUR_NAME`, `YOUR_ROLE`, `YOUR_TAGLINE`
   - the five `YOUR_...` values in **About me**
2. On GitHub, create a **public** repository whose name exactly matches your username. For example, user `octocat` must create repository `octocat`.
3. Upload this folder's contents to the root of that repository. Keep `.github/workflows/` exactly as provided.
4. Create the token needed for the detailed metrics:
   - GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens**.
   - Select your profile repository and grant read access to account/repository metadata. If you want private-repository data included, grant read access to those repositories too.
   - In the profile repository, go to **Settings** → **Secrets and variables** → **Actions** → **New repository secret**.
   - Name it `METRICS_TOKEN` and paste the token value.
5. Open the repository's **Actions** tab. Run both workflows manually once:
   - `Generate GitHub metrics`
   - `Generate contribution snake`
6. Refresh your GitHub profile after both workflows finish. The metrics file will appear on the default branch; the snake files will appear on the `output` branch.

## Troubleshooting

- If a workflow cannot commit, open **Settings → Actions → General → Workflow permissions**, select **Read and write permissions**, and save.
- If `github-metrics.svg` shows a token error, recreate `METRICS_TOKEN` and confirm the token can read the repositories you want counted.
- Language percentages are based on detected code size across repositories, not time spent coding. The eight largest languages are listed; smaller ones are grouped into **Other**.
- Private contributions can be counted only when your token has permission to read the relevant private repositories. Never paste the token into `README.md` or a workflow file.
