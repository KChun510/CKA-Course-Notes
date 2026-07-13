# Secrets Shhhhh....

- Config map not the right place for paswd.

## Using secrects
- Imparative:
    - `Kubectl creat secre generic <secret-name> --from-literal=<k>=<v>`

- Declarative:
    - `kubectl create -f`
    - Via a secret file
    - !Must write in/ pass in an encoded format.!

# How to encode pawrds

```bash
echo -n 'mysql' | base64
echo -n 'root' | base64
echo -n 'paswrd' | base64
```

Outputs:

```text
bXlzcWw=
cm9vdA==
cGFzd3Jk
```

To decode:

```bash
echo 'bXlzcWw=' | base64 --decode
echo 'cm9vdA==' | base64 --decode
echo 'cGFzd3Jk' | base64 --decode
```

Or with the shorter decode flag:

```bash
echo 'cGFzd3Jk' | base64 -d
```

Use `-n` during encoding so `echo` does not include a newline character.


