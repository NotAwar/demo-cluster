# Notes

## manual configs done

- Added secret for ghcr auth
- Added secret for GitHub auth / flux bootstrap

## Port forwarding for UIs

- kagent UI: `kubectl port-forward -n kagent svc/kagent-ui 8080:8080` - exposes kagent UI on http://localhost:8080
- flux operator UI: `kubectl port-forward -n flux-system svc/flux-operator-webui 9080:9080` - exposes flux operator UI on http://localhost:9080