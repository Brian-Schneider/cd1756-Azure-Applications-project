# Article CMS Project Write-up

### Analyze, choose, and justify the appropriate resource option for deploying the app.

#### Analysis of VM vs App Service

**Virtual Machine (VM)**:
- *Costs*: Higher costs due to continuous running regardless of traffic. Requires full OS licensing and maintenance costs.
- *Scalability*: Manual scaling or using VM scale sets. More control but requires more management.
- *Availability*: Requires additional configuration for high availability (99.95% with availability sets).
- *Workflow*: More complex deployment process, requires infrastructure management.
- *Control*: Full control over OS and environment.

**App Service**:
- *Costs*: Lower costs with consumption-based pricing. Free tier available for development.
- *Scalability*: Built-in auto-scaling capabilities. Easy horizontal and vertical scaling, but with some limitations on for the App Service Plan (maximum of 14GB of memory and 4 vCPU).
- *Availability*: High availability (99.95%) built-in with automated management.
- *Workflow*: Streamlined deployment with direct Git integration and DevOps support.
- *Control*: Limited control over host environment but sufficient for web applications, but only for a set of programming languages.

#### Choice: App Service

For this CMS application, I choose Azure App Service as the deployment solution.

#### Justification:

1. **Application Type**: The CMS is a Python Flask web application that doesn't require specialized system configurations, making it perfect for App Service's PaaS environment.

2. **Cost Efficiency**: 
   - App Service offers pay-as-you-go pricing
   - No need to pay for unused server capacity
   - Built-in infrastructure management reduces operational costs

3. **Development Workflow**:
   - Easy integration with Git for continuous deployment
   - Built-in support for Python and pip requirements
   - Simplified SSL certificate management

4. **Maintenance**:
   - Automated OS updates and patches
   - Built-in load balancing and traffic management
   - No need for infrastructure management

5. **Security**:
   - Built-in Azure AD integration
   - SSL/TLS support
   - Network isolation capabilities

### Assess app changes that would change your decision.

I would consider switching to a VM solution if the application requirements changed in the following ways:

1. **Custom System Requirements**:
   - Need for specific OS configurations
   - Custom system-level software requirements
   - Special hardware requirements

2. **Performance Demands**:
   - Need for specialized hardware (GPU, high-memory instances)
   - Requirements for specific network configurations
   - Custom caching or database configurations

3. **Regulatory Requirements**:
   - Strict data sovereignty requirements
   - Need for complete control over the hosting environment
   - Specific security protocols that require OS-level access

4. **Scale and Architecture Changes**:
   - Migration to a microservices architecture requiring complex networking
   - Need for specialized load balancing
   - Requirements for specific server clustering configurations

5. **Cost Considerations at Scale**:
   - If the application grows to a point where VM costs become more economical
   - Need for reserved instances with predictable, high-volume traffic

### Python App Service URL.

   - https://udacityprojectcms.azurewebsites.net/