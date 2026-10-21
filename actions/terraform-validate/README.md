## Terraform Init and Validate

Validates a Terraform root configuration by checking formatting,
initializing providers and modules, and validating configuration.

### Usage

```yaml
- name: Terraform Init and Validate
  uses: YOUR_ORG/terraform-actions/actions/terraform-validate@v1.0.0
  with:
    working_directory: modules/cognito
    terraform_version: "1.14.6"
```

### Inputs

| Input             | Required | Default | Description              |
| ----------------- | -------- | ------- | ------------------------ |
| working_directory | Yes      | —       | Terraform root directory |
| terraform_version | No       | 1.14.6  | Terraform CLI version    |

### Checks

- `terraform fmt -check -diff -recursive`
- `terraform init -backend=false -input=false`
- `terraform validate -no-color`
