---
title: SSO Integration
status: approved
---

# SSO Integration

## Overview
Add enterprise SSO support to TinkerSystems using SAML 2.0 and OIDC,
enabling customers to use their existing identity providers.

## Security Requirements

### Session Management
- Sessions must expire after 8 hours of inactivity
- Concurrent session limit of 3 per user
- Session tokens must be rotated every 30 minutes

### Authentication
- MFA must be enforced for all admin accounts
- Password fallback disabled when SSO is configured
- Failed login lockout after 5 attempts within 10 minutes

### Token Security
- All tokens must be signed using RS256
- Refresh tokens must be single-use (rotate on every refresh)
- Token revocation must propagate within 60 seconds
