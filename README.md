# 🛡️ Next-Gen 2-of-3 MPC Wallet Architecture [Conceptual Overview]

Welcome to the discussion on our upcoming high-security wallet architecture. We are building a non-custodial wallet framework that completely eliminates the traditional private key vulnerability by leveraging Multi-Party Computation (MPC) and a Threshold Signature Scheme (TSS).

## 🏗️ Core Architecture: The 3 Shards
Instead of generating a monolithic private key, the cryptographic initialization outputs 3 distinct shards. A 2-out-of-3 threshold is required to sign any transaction, ensuring no single point of failure.

- **Shard A (Client):** Secured via TEE/Secure Enclave on the mobile device.
- **Shard B (Co-Signer):** Hosted on secure distributed infrastructure, executing dynamic risk-engine checks before allowing a partial signature.
- **Shard C (Recovery):** A fully encrypted backup matrix controlled by the user.

## ⚙️ Transaction Flow (Zero-Knowledge Signing)
1. Transaction initiated on the Client application.
2. Client generates `Partial_Signature_A` locally.
3. Client requests the Co-Signer for `Partial_Signature_B` (subject to biometric/auth/IP-fencing checks).
4. The partial signatures are mathematically combined to form a valid ECDSA/EdDSA signature.
5. **The full private key is never reconstructed or held in memory.**

*(Watch the attached conceptual video for a visual representation of the cryptographic flow!)*
