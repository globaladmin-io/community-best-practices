# Opinionated Global Admin security best practices

> Note: This project is not associated with, or endorsed by Microsoft

## Why this page?

Microsoft maintains [their recommended security best practices](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/best-practices) but those can't be applied in all cases, and sometimes those roles shouldn't be followed at all because the recommendations make each other impossible to follow. 

### Proof #1

Limit the number of Global Administrators to less than 5

![image](https://github.com/user-attachments/assets/c0e8e506-4c56-4e83-8f27-93968e9efbca)

_In some cases one might take this recommendation as a hard limit, but how could you apply this rule at an organization which follows a `24/7` operating model with support group members at least in three locations, where maintaining a healthy workload - allowing people to go on vacation with someone else being available - is a must? In this case they would need at least 3 x 2 = 6 people being assigned the Global admin role. Which is already 50% more people than what Microsoft recomments._

### Proof #2

Limit the number of privileged role assignments to less than 10

_When you want to follow the least privileged security practices and have at least 2 people on your team you can only assign them 4-5 roles and than you'll run unti the "less than 10" limit._

> Important: Be aware that not **everything** on this page will apply to all organizations, because organizations come in all kinds of size and shape, the same way the official guidance written and published by Microsoft itself won't or could be apply in all cases.

## Real life best practices

Let's get to those "Opinionated" security best practices, since you are reading this page to get to them, right? 

But before we do, here are two notices:

> Notice #1: THE INFORMATION IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
 
> Notice #2: Be aware that not **everything** on this page will apply to all organizations, because organizations come in all kinds of size and shape, the same way the official guidance written and published by Microsoft itself won't or could be apply in all cases.

### Our options

From the following unordered options, we can select those that make sense to our risk appetite and operational model:

- phishing resistant authentication
- privileged identity management
- dedicated admin account
- conditional access policy for compliant device
- conditional access policy for trusted network location
- dedicated privileged admin workstation

## Controls, boundaries, exposures

### PIM is not a security boundary

A security boundary in Microsoft documentation generally refers to something that enforces strong isolation between different trust zones (e.g., tenant boundaries, identity authentication protections, etc.). PIM doesn’t provide that kind of isolation on its own. Instead:

- PIM is a governance and access control service designed to help you manage and reduce standing privileged access by using just-in-time (JIT) activation, approval workflows, MFA requirements, and auditing.
- It reduces risk by limiting when and how users can activate privileged roles, but it isn’t itself a security perimeter that stops attackers who already have valid authentication and certain privileges.

**Exposure:** the risk remains: if a PIM-eligible account is compromised by other means, it can be used to abuse the privileges it holds.

> Because PIM isn’t a security boundary by itself, Microsoft and security practitioners recommend using PIM as part of a layered identity security strategy - with Conditional Access, MFA, privileged access workstations (PAWs), monitoring, and alerting - to achieve stronger overall protection.


## More to come

Later. 
