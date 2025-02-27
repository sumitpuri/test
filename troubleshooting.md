# Troubleshooting

### Step 1 - Finding the issue

Navigate to Installed Operators > IBM TRIRIGA Application Suite > Tririga to view all the TRIRIGA instances

<img width="1151" alt="image" src="https://github.com/user-attachments/assets/fed76549-2876-49b8-a242-fc5def7357d9">

Click on `tas-oob` and scroll to the bottom to review the failure cause

<img width="1151" alt="image" src="https://github.com/user-attachments/assets/73b8f024-e897-4be4-841b-5ea0390b97fa">




### Step 2 - Understanding the issue

> NOTE: `vault_secret` is the new TRIRIGA property introduced in TAS 11.6 for AES Encryption.

### Step 3 - Resolving the issue

Create a secret `tas-vault-secret`

Click on the `+` sign to add 

<img width="1151" alt="image" src="https://github.com/user-attachments/assets/fa10c7cd-5f13-4864-9804-a519fbd7ee68">

Copy/paste below

```
kind: Secret
apiVersion: v1
metadata:
  name: tas-vault-secret
  namespace: ibm-tas
stringData:
  password: 1Password*
```

Click Installed Operators > IBM TRIRIGA Application Suite > Tririga > `tas-oob`. Go to YAML

<img width="1146" alt="image" src="https://github.com/user-attachments/assets/dcc20052-6f93-4843-8595-6ba90cb4cf7a">

Change the `vault_secret` value from `na` to `tas-vault-secret` and click Save.

<img width="311" alt="image" src="https://github.com/user-attachments/assets/987c012b-1a6b-4cd5-9cf2-7de61a25ae56">


### Step 4 - Monitor the progress

Review the `tas-oob` instance to confirm that error has been resolved

<img width="1151" alt="image" src="https://github.com/user-attachments/assets/ab68fdd8-613b-43a9-9eb1-217b2a696507">









