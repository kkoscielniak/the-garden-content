---
title: First test in Cypress
---

> [!tip] Keep in mind the tested application needs to be running in the background

```tsx
describe("anonymous calculator", () => {
  it("can make calculations", () => {
    cy.visit("/");
    cy.findByText(/^1$/).click();
    cy.findByText(/^\+$/).click();
    cy.findByText(/^2$/).click();
    cy.findByText(/^=$/).click();
    cy.findByTestId("total").should("have.text", "3");
  });
});
```
