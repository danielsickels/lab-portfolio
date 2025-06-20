# CompTIA A+ Troubleshooting Methodology

## Overview

This guide outlines the **CompTIA A+ 220-1101 troubleshooting methodology** - a systematic 10-step process for resolving technical issues efficiently and effectively. This methodology ensures thorough problem resolution while maintaining system integrity and preventing future occurrences.
Note: These steps are outlined in a course created by professor messer, provided via YouTube. An example we follow is illustrated within the video.

---

## The 10-Step Troubleshooting Process

### **Step 1: There is an Issue**

> _"We start with a system or application that's broken..."_

**Dissection**: This is the **trigger** point. The system isn't behaving as expected, and action is needed. Recognition of the problem initiates the troubleshooting process.

**Key Actions**:

- Acknowledge the problem exists
- Understand the impact on users/business
- Determine urgency and priority level

---

### **Step 2: Identify the Problem**

> _"Collect as much information as possible..."_ > _"Get screenshots, error messages, speak with users, check logs, and review change documentation."_

**Dissection**: This step is about **gathering context** — user reports, symptoms, system logs, and recent changes. Effective troubleshooting starts with a complete understanding of **what's wrong and when it started**.

**Key Actions**:

- Interview users about symptoms and timeline
- Collect error messages and screenshots
- Review system logs and event viewer
- Check recent changes or updates
- Document initial symptoms and conditions

---

### **Step 3: Establish a Theory of Probable Cause**

> _"Start theorizing on what the root cause might be..."_ > _"Occam's razor, common causes first, list of potential causes."_

**Dissection**: Generate **logical hypotheses**. Start with the obvious (e.g., unplugged cable) and move to complex causes. Theories should be **ranked** from most to least likely.

**Key Actions**:

- List potential causes from most to least likely
- Apply Occam's Razor (simplest explanation first)
- Consider common failure points
- Research known issues for similar symptoms

---

### **Step 4: Test the Theory**

> _"Test our theory to see if we found the problem..."_ > _"If power cord is fine, try the next theory..."_

**Dissection**: **Validate hypotheses** one by one. Each test either rules out a possibility or confirms a cause. If no theory works, reassess or escalate.

**Key Actions**:

- Test each theory systematically
- Use appropriate diagnostic tools
- Document test results
- Move to next theory if current one fails

---

### **Step 5: Evaluate Results: Is It Working?**

> _"If one of the theories resolves the problem, move to the next step..."_ > _"If not, go back and retest or consider new theories."_

**Dissection**: A simple **decision gate**. Did your test solve the issue? If yes, proceed. If not, cycle back to Step 3 to adjust your theory.

**Key Actions**:

- Determine if the issue is resolved
- If resolved, proceed to implementation planning
- If not resolved, return to Step 3 for new theories
- Consider escalation if all theories exhausted

---

### **Step 6: Establish a Plan of Action**

> _"Create a plan for implementing that fix in your production environment..."_ > _"Include rollback procedures and vendor recommendations."_

**Dissection**: Create a **structured implementation plan**. Include contingencies and rollback options in case the fix introduces new problems.

**Key Actions**:

- Document the exact steps to implement the fix
- Include rollback procedures
- Review vendor documentation and recommendations
- Schedule implementation during appropriate maintenance window
- Prepare necessary resources and tools

---

### **Step 7: Implement the Plan**

> _"Implement that change on our environment..."_ > _"Use the change control window and required resources."_

**Dissection**: **Execute the fix** during an authorized window. Efficiency and precision are key, especially in time-constrained environments.

**Key Actions**:

- Follow the established plan step-by-step
- Use proper change control procedures
- Monitor for any unexpected issues
- Document any deviations from the plan

---

### **Step 8: Verify Full System Functionality**

> _"Perform some tests... confirm that the original problem was resolved..."_ > _"Implement preventative measures if possible."_

**Dissection**: Confirm not only that the **symptom is gone**, but that the **system as a whole is functioning**. Preventive steps (like updates or alerts) are good practice here.

**Key Actions**:

- Test the specific issue that was reported
- Verify overall system functionality
- Check for any new issues introduced by the fix
- Implement preventive measures if applicable
- Update monitoring and alerting systems

---

### **Step 9: Document Findings**

> _"Document everything... so we know how to fix it next time..."_ > _"Use help desk or knowledge-base software."_

**Dissection**: This step ensures the **institutional memory** is preserved. Good documentation enables faster resolution in future occurrences.

**Key Actions**:

- Document the complete troubleshooting process
- Record the root cause and solution
- Update knowledge base and help desk systems
- Share findings with team members
- Create or update runbooks for similar issues

---

### **Step 10: "Yay, it works!"**

> _"So there's our troubleshooting process... and we fixed the issue."_

**Dissection**: This is the **confirmation and closure** stage. All testing is passed, documentation is complete, and the issue is resolved. Time to celebrate the win (responsibly)!

**Key Actions**:

- Confirm with users that the issue is resolved
- Close the incident ticket
- Update any status pages or communications
- Conduct post-incident review if necessary
- Celebrate the successful resolution

---

## Practical Example: "Desktop Won't Power On"

### **Step 1: There is an Issue**

- User reports desktop computer will not turn on
- No power indicator lights, no fan noise, no display

### **Step 2: Identify the Problem**

- **Gather Information**:
  - When did this start? (This morning, after power outage, etc.)
  - Any recent changes? (Moved computer, new hardware, etc.)
  - Any error messages before it stopped working?
  - Does the power supply have a light indicator?

### **Step 3: Establish a Theory of Probable Cause**

**Ranked from most to least likely**:

1. **Power cable unplugged or loose** (most obvious)
2. **Power supply failure** (common hardware failure)
3. **Power outlet/electrical issue** (environmental)
4. **Motherboard failure** (less common)
5. **CPU or RAM failure** (least likely for no power)

### **Step 4: Test the Theory**

**Test 1 - Power Cable**:

- Check if power cable is properly connected to computer and outlet
- Try a different power cable if available
- Test outlet with another device

**Test 2 - Power Supply**:

- If cable is good, test power supply with multimeter
- Check for bulging capacitors or burnt smell
- Try a known-good power supply

**Test 3 - Electrical**:

- Test outlet with voltage tester
- Try different outlet or surge protector
- Check circuit breaker

### **Step 5: Evaluate Results**

- **If power cable was loose**: Issue resolved, proceed to Step 6
- **If power supply failed**: Issue identified, proceed to Step 6
- **If outlet is dead**: Issue identified, proceed to Step 6
- **If none of above**: Return to Step 3 for new theories

### **Step 6: Establish a Plan of Action**

**If power supply failed**:

- Research compatible replacement power supply
- Order replacement with proper wattage and connectors
- Plan installation during maintenance window
- Prepare backup plan if replacement doesn't work

### **Step 7: Implement the Plan**

- Install new power supply following safety procedures
- Connect all power cables properly
- Test basic functionality

### **Step 8: Verify Full System Functionality**

- Confirm computer powers on normally
- Test all components (CPU, RAM, storage, graphics)
- Run system diagnostics
- Update power supply monitoring if available

### **Step 9: Document Findings**

- Document that power supply failure was root cause
- Note symptoms and resolution steps
- Update inventory with new power supply
- Create knowledge base article for similar issues

### **Step 10: "Yay, it works!"**

- Confirm with user that desktop is working
- Close support ticket
- Update any status communications
- Successfully resolved power supply failure

---

## Troubleshooting Process Summary

| Step | Description           | Key Focus                                    |
| ---- | --------------------- | -------------------------------------------- |
| 1    | There is an issue     | Problem recognition and acknowledgment       |
| 2    | Identify the problem  | Information gathering and context collection |
| 3    | Establish a theory    | Hypothesis generation and prioritization     |
| 4    | Test the theory       | Systematic validation of each hypothesis     |
| 5    | Evaluate results      | Decision point - resolved or continue        |
| 6    | Create plan of action | Structured implementation planning           |
| 7    | Implement solution    | Controlled execution of the fix              |
| 8    | Verify functionality  | Comprehensive testing and validation         |
| 9    | Document findings     | Knowledge preservation and sharing           |
| 10   | Yay it works!         | Confirmation and closure                     |

---

## Best Practices

### **Always Start Simple**

- Check the obvious first (cables, power, basic settings)
- Don't assume complex problems without ruling out simple causes

### **Document Everything**

- Record each step, test, and result
- This helps with future troubleshooting and team knowledge

### **Use Systematic Approach**

- Don't skip steps or jump to conclusions
- Each step builds on the previous one

### **Consider User Impact**

- Balance thoroughness with urgency
- Communicate progress to stakeholders

### **Learn from Each Issue**

- Every problem is an opportunity to improve processes
- Update documentation and procedures based on findings

---

## Common Troubleshooting Tools

### **Hardware Tools**

- Multimeter for electrical testing
- Screwdrivers and basic hand tools
- Spare cables and components for testing

### **Software Tools**

- Event Viewer for Windows logs
- Device Manager for hardware status
- System Information for configuration details
- Diagnostic software (MemTest86, Prime95, etc.)

### **Documentation Resources**

- Manufacturer documentation
- Knowledge base articles
- Vendor support resources
- Team runbooks and procedures

This methodology provides a structured approach to troubleshooting that can be applied to virtually any technical issue, ensuring consistent and effective problem resolution.
