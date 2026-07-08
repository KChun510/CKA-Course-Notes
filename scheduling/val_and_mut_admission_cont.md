# Admission Controller
- Plugins:
    - Defaultstorageclass
        - Submit req to create a PVC.
        - Module that validates, but can also change/ mutate the object/ image itself.

## Quick summary:
- There are two kinds of admission controllers
1) `Mutating`
    - Changes, the requested object
2) `Validating`

# Web-Hooks, for both kinds of controllers
1) `MutatingAdmissionWebhook`
2) `ValidatingAdmissionWebook`

## Summary:
- Default shape/ json blob sent to your server.
- Server meant to respond in a default response.
    
