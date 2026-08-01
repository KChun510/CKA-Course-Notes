# How to mangage certs and use cert API

## Scenario
- There is a new admin, that needs a new key pair to access cluster/ kube-api
    - They will create their own private key.
    - And a signing request, that gets sent to main admin
        - Main admin, signs it via internal CA serve
        - Gives it back to new admin
- Doing this manually will be to much to keep track of.
- Solution, use the cert API

## Solution
- Main admin creates  a new recourse called `CertificateSigningRequest` object
- Review request
- Approve request 
- Share certs to user

### Workflow:
1) User first creates a key, and a csr.
2) Sends csr to admin
3) admin creates a new `CertificateSigningRequest` resource 
    - Pass in the CSR, via base 64 encoding
4) `kubectl get csr` ( Will now be listed )
    - Can approve via `kubectl certificate approve jane`
    - `kubectl get csr jane -o yaml`


