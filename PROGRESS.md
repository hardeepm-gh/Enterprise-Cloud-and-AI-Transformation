# 🚀 Terraform 30-Day Challenge: Progress Log

## 📅 Day 20: The Modular Architecture & The Great Recovery
**Date:** February 13, 2026
**Status:** COMPLETED ✅

### 🏗️ Infrastructure Changes
- **Modularized VPC:** Refactored a flat `main.tf` into a reusable `modules/vpc/` directory.
- **Output Handoffs:** Implemented module outputs to pass the `vpc_id` and `subnet_id` to the Root module for RDS consumption.
- **Resource Cleanup:** Manually verified AWS account state using CLI (`aws ec2 describe-vpcs`) to ensure $0 spend over the weekend.

### 🧠 Key Learnings
- **Encapsulation:** Child modules are private; outputs are the "public API" of a module.
- **Disaster Recovery:** Managed a full **Terraform Crash (Panic)** by nuking `.terraform` and `.terraform.lock.hcl` to reset the local provider state.
- **Manual Intervention:** Learned that when automation fails, the AWS Console and CLI are the ultimate sources of truth.

### 🚧 Challenges Overcome
- Resolved "Unsupported attribute" errors by correctly mapping module outputs.
- Fixed a "duplicate resource" bug in the VPC module using `grep` debugging.

### 🎯 Next Goal
- **Day 21 (Monday):** Create a **Compute Module (EC2)** and practice **Module Composition** (linking the Network module to the Compute module).
