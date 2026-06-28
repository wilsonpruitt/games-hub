# Deploying the games hub → games.wrootlabs.com

Static directory page (`index.html`) linking out to **pessoi.com** and
**playhoshi.com**. No build.

## First deploy
```sh
cd ~/wrootgames/games-hub
npx vercel            # prompts:
#   Set up and deploy?        yes
#   Which scope?              <your Wroot Labs team>  (team_sERwO8GidBZdsL7F1I6fcgAW)
#   Link to existing project? no
#   Project name?             games-wrootlabs
#   Code directory?           ./
#   Modify settings?          no
npx vercel --prod
```

## Point games.wrootlabs.com at it  (protected — your call)
**Project → Settings → Domains → Add `games.wrootlabs.com`.**
It's a subdomain, so a single CNAME does it:
- `CNAME` `games` → `cname.vercel-dns.com`

If wrootlabs.com is already on Vercel (its nameservers), adding the domain
in the project wires the record automatically — nothing to do at a registrar.

## Re-deploy after edits
```sh
cd ~/wrootgames/games-hub && npx vercel --prod
```
