# Packer Build for Ubuntu and RHEL on AWS

This repository contains Packer configurations for building custom machine images (AMIs) for Ubuntu Server 22.04 LTS and Red Hat Enterprise Linux 9 on Amazon Web Services (AWS). The machine images are configured for optimal performance and security.

## Prerequisites

Before you begin, ensure you have the following tools installed on your local machine:

- [Packer](https://www.packer.io/) (version 1.7.0 or later)
- [AWS CLI](https://aws.amazon.com/cli/) (version 2.0 or later)
- AWS Access Keys with sufficient permissions to create AMIs

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/rsergio07/packer-on-aws.git
cd packer-on-aws
```

### Configure AWS Credentials

Ensure your AWS CLI is configured with the necessary credentials:

```bash
aws configure
```

### Build the AMI

To build an AMI for Ubuntu Server 22.04 LTS:

```bash
packer build -var 'ami_name=custom-ubuntu-22.04' ubuntu-22.04.json
```

To build an AMI for Red Hat Enterprise Linux 9:

```bash
packer build -var 'ami_name=custom-rhel-9' rhel-9.json
```

## Configuration Details

- `ubuntu-22.04.json`: Configuration file for building an Ubuntu Server 22.04 LTS AMI.
- `rhel-9.json`: Configuration file for building a Red Hat Enterprise Linux 9 AMI.

### Variables

- `ami_name`: The name of the AMI to be created.

## Usage Instructions

1. **Clone the repository and navigate to the directory:**
   ```bash
   git clone https://github.com/rsergio07/packer-on-aws.git
   cd packer-on-aws
   ```

2. **Configure AWS credentials:**
   ```bash
   aws configure
   ```

3. **Build the desired AMI:**
   ```bash
   packer build -var 'ami_name=custom-ubuntu-22.04' ubuntu-22.04.json
   ```
   or
   ```bash
   packer build -var 'ami_name=custom-rhel-9' rhel-9.json
   ```

## Testing and Validation

After building the AMI, you can test it by launching an EC2 instance using the newly created AMI. Ensure all services and configurations are working as expected.

## Security Considerations

- Handle AWS credentials securely by using environment variables or AWS IAM roles.
- Ensure the AMIs are hardened according to security best practices.

## Troubleshooting

If you encounter issues, check the following:

- Ensure your AWS credentials are correctly configured.
- Verify that you have sufficient permissions to create AMIs.
- Review the Packer build logs for any errors.

## Feedback and Contributions

I welcome feedback, suggestions, and contributions. If you encounter issues or have ideas for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE). See the [LICENSE](LICENSE) file for details.

If you have any questions, feel free to reach out.

---
