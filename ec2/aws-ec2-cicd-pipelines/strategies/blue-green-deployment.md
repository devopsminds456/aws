# Blue-Green Deployment

## Overview
Deploy new version alongside old version, then switch traffic.

## Steps
1. Maintain two environments (Blue = current, Green = new).
2. Deploy new release to Green.
3. Switch traffic via Load Balancer or Route 53.

## Benefits
- Zero downtime deployments
- Easy rollback

## Risks
- Higher infrastructure costs.

