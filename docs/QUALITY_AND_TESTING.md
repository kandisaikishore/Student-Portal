# Development, Testing, and Student-Data Security Guide

Student Portal is a student-focused application workspace. Check the current source to confirm implemented roles, modules, and persistence behavior.

## Setup

```bash
git clone https://github.com/kandisaikishore/Student-Portal.git
cd Student-Portal
```

Use the project's declared dependency manager, runtime, and scripts. Configure local credentials without committing secrets or real student records.

## Functional QA

For implemented workflows, test:
- Required student fields and invalid identifiers
- Create, view, update, and delete operations where supported
- Duplicate student records and missing resources
- Empty/loading/error states and failed saves
- Refresh/restart behavior based on the actual persistence layer
- Keyboard navigation, accessible form labels, and responsive layouts

## Authorization and privacy

If roles such as student, staff, or administrator exist, enforce permissions on the server for every protected operation. Test allowed and denied access, including attempts to view or edit another student's record by changing an identifier. Do not treat a hidden button as an authorization control.

Avoid logging student names, contact details, academic records, or credentials unless essential and explicitly protected. Document data storage, export, deletion, and retention behavior from the actual implementation.

## Pull-request checklist

- [ ] Add regression tests for the changed student workflow.
- [ ] Run the declared lint/test/build commands.
- [ ] Test permission boundaries for any protected records.
- [ ] Use synthetic data in fixtures and screenshots.
- [ ] Document checks that could not be run.
