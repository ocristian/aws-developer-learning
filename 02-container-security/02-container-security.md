# Container Security

## Risks

Containerized environments introduce unique security challenges. Risks can be grouped under the core principles of **Confidentiality**, **Integrity**, and **Availability**.


### Confidentiality

Ensuring proper isolation and access control is essential to protect sensitive data.

**Isolation Boundaries:**

- **Container-to-Container:** Prevent unauthorized communication or shared resources.
- **Process-to-Process:** Ensure processes inside a container cannot interfere with others.
- **Container-to-External World:** Control outbound and inbound data flow.

**Access Control:**

- **Who** has access, **when**, and **where**
- Enable **audit logging** for container lifecycle events
- Control container **start/stop** permissions
- Secure and limit access to **container content**

**Resource Usage:**

- Limit CPU, memory, and I/O to prevent abuse or denial-of-service scenarios.


### Integrity

Protecting containers from unauthorized changes or tampering:

- Use signed and verified container images.
- Regularly scan images for vulnerabilities.
- Avoid using mutable base images or packages from untrusted sources.


### Availability

Ensure containers are resilient and do not expose the system to unnecessary risks:

- Build **minimal containers** with only the required components.
- Avoid adding tools like `openssh`; containers should not allow SSH access.
- Use `docker exec` or `kubectl exec` for shell access instead of remote logins.
- Restrict unnecessary outbound communications.
- Remember: **Container technology does not imply network encryption**—use proper TLS or VPNs.


> Security should be enforced at build-time, deploy-time, and runtime.
