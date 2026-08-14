# ZPA Application Connectivity Troubleshooting

## Overview

Zscaler Private Access (ZPA) provides secure access to private applications without placing users directly on the corporate network.

When a user cannot access a private application, troubleshooting should validate the complete path from the user's Zscaler Client Connector through ZPA policy, App Connectors, DNS, and the backend application.

## Troubleshooting Flow

User
  ↓
Zscaler Client Connector
  ↓
ZPA Service Edge
  ↓
Access Policy
  ↓
App Connector
  ↓
DNS Resolution
  ↓
Private Application

## 1. Verify Zscaler Client Connector

Confirm:

- User is authenticated
- ZPA service is enabled
- Client Connector is connected
- Correct user identity is displayed
- No authentication errors are present

## 2. Verify Application Segment

Check:

- Application FQDN
- IP address
- TCP/UDP port
- Application segment configuration
- Segment group assignment

Incorrect application definitions can prevent ZPA from identifying and forwarding the traffic correctly.

## 3. Validate Access Policy

Confirm that the user matches the required ZPA access policy.

Review:

- User
- User group
- Application segment
- Device posture
- Location
- Authentication conditions

## 4. Check App Connector Health

Verify that the App Connectors assigned to the application are healthy.

Check:

- Connector status
- Connector group
- Network connectivity
- Resource utilization
- Application reachability

## 5. Validate DNS

The App Connector must be able to resolve the private application's hostname when FQDN-based application definitions are used.

Validate:

```bash
nslookup application.example.internal
