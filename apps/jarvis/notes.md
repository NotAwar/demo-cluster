# Notes and Best Practices

#

# 1. Certificate Format

# - Must be in PEM format (text-based, base64-encoded)

# - Starts with -----BEGIN CERTIFICATE-----

# - Ends with -----END CERTIFICATE-----

# - No extra whitespace or characters

#

# 2. Secret Management

# - Store Secrets in the same namespace as ModelConfig

# - Use descriptive names (e.g., "litellm-ca-cert" not "secret1")

# - Rotate certificates before expiration

# - Never commit Secrets to Git (use sealed secrets or external secret management)

#

# 3. Security

# - Always enable verification (disableVerify: false) in production

# - Use RBAC to limit Secret access to specific service accounts

# - Use namespace isolation for different environments

# - Monitor certificate expiry dates

#

# 4. Testing

# - Test connectivity after configuration changes

# - Check agent logs for TLS warnings or errors

# - Verify certificate chain with openssl commands

# - Use verification disabled mode only for development/testing

#

# 5. Certificate Updates

# - Update Secret with new certificate

# - Restart agent pods to pick up changes: kubectl rollout restart deployment/agent-<name>

# - Secrets are mounted as volumes and not automatically reloaded

#

# 6. Troubleshooting

# - See <https://kagent.dev/docs> for detailed debugging steps

# - Check agent logs: kubectl logs deployment/agent-<name>

# - Verify Secret is mounted: kubectl exec deployment/agent-<name> -- ls /etc/ssl/certs/custom/

# - Test certificate: kubectl exec deployment/agent-<name> -- openssl x509 -in /etc/ssl/certs/custom/ca.crt -text -noout
