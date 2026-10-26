## Step 1: Create or Select a Learning Account

### Objective

Prepare an authorized AWS learning environment and confirm which identity I am using.

### Steps

1. **Create an AWS account only if I do not already have a suitable learning account.**
   I already had an AWS account, so I used it instead of creating a new one.

2. **Review current AWS pricing and Free Tier terms.**
   Eligibility and included usage can change, so I read the current terms on the official AWS Free Tier page and on the Free Tier page in the Billing and Cost Management console.

3. **Keep account contact and recovery information accurate.**
   I checked that the account email and phone number are correct and that I can access both. I also reviewed the alternate contacts.

4. **Use a unique password stored in a password manager.**
   The root password is unique, long, and stored in a password manager.

5. **Use root only for tasks that require root credentials.**
   Root is treated as break-glass access. Daily work is done with an IAM user or role.

6. **Do not create root access keys.**
   I confirmed on the Security credentials page that no root access keys exist.

7. **If using the AWS CLI, install CLI v2 and configure an approved profile.**
   Temporary credentials are preferred where practical.

   ```bash
   aws --version
   aws configure --profile <PROFILE_NAME>
   aws sts get-caller-identity --profile <PROFILE_NAME>
   ```

   The ARN returned by `get-caller-identity` should be an IAM user or role, **not** `:root`.

8. **Do not put account IDs, contact details, or billing data in this public repository.**
   I use placeholders and blur or crop screenshots before committing them.

---

## Checklist

- [ ] Using an existing, suitable learning account (or created a new one)
- [ ] Reviewed current AWS pricing and Free Tier terms
- [ ] Contact and recovery information is accurate
- [ ] Root password is unique and stored in a password manager
- [ ] MFA is enabled on the root user
- [ ] No root access keys exist
- [ ] Root is used only when required
- [ ] AWS CLI v2 installed and a profile configured (if using the CLI)
- [ ] Confirmed my identity is not root
- [ ] No sensitive data committed to this repository

---

## Free Tier Summary

*Write 1 to 2 sentences in your own words.*

> I reviewed the current AWS Free Tier terms on the AWS website and in the Billing console. My account is on the **[plan type]**. It includes **[what is included and for how long]**. If I exceed the limits, **[what happens]**. IAM itself has no charge.

---

## Evidence (redacted)

| Item | Evidence |
|------|----------|
| Free Tier reviewed | Summary above |
| Root MFA enabled | Statement or redacted screenshot |
| No root access keys | Statement or redacted screenshot |
| Identity confirmed | Output of `aws sts get-caller-identity` with the account ID replaced |

Example of redacted output:

```json
{
    "UserId": "AIDAEXAMPLEEXAMPLE",
    "Account": "<ACCOUNT_ID>",
    "Arn": "arn:aws:iam::<ACCOUNT_ID>:user/<IAM_USER_NAME>"
}
```

---

## Key Lessons

- Root is for rare account-level tasks only, never for daily work.
- Root access keys should never exist.
- Free Tier terms change, so always read the current ones.
- Public repositories must never contain account IDs, contact details, billing data, or keys.

---

> **Privacy note:** This is a public repository. All account IDs, email addresses, phone numbers, billing details, and access keys are redacted or replaced with placeholders such as `<ACCOUNT_ID>`.
