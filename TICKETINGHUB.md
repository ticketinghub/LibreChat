## Deployment

Deploy to Railway using the template.

Add config in base64 encoding to `LIBRECHAT_YAML_B64` env var.

```sh
base64 -i librechat.prod.yaml | tr -d '\n' > librechat.prod.yaml.b64
```

Change LibreChat service start script on Railway:

```sh
sh -lc 'echo "$LIBRECHAT_YAML_B64" | base64 -d > /app/librechat.yaml && exec npm run backend'
```

## Config

- Set `APP_TITLE`, `CUSTOM_FOOTER`, `HELP_AND_FAQ_URL`
- Remove `termsOfService` from config
- Edit in config: `interface`
