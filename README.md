# temp-doc
Welcome to the Enzyme to React Testing Library migration guide. This document aims to assist developers in smoothly transitioning from the Enzyme testing library to React Testing Library (RTL). As software development practices evolve, the React Testing Library has gained popularity for its user-centric testing approach, focusing on behavior rather than implementation details. This migration is driven by the desire to align with best practices, enhance test readability, and improve the overall testing experience.

    1. Purpose
        a) Improved Test Readability: The React Testing Library encourages tests that closely mimic how users interact with the application. This shift enhances the readability of tests by focusing on the end-user experience rather than the internal component structure.
        b) User-Centric Testing: React Testing Library promotes a user-centric testing philosophy, emphasizing the testing of components based on their rendered output and user interactions. This approach aligns more closely with real-world scenarios, leading to more meaningful and reliable tests.
        c) Community Adoption and Support: React Testing Library has gained widespread adoption within the React community and is actively maintained. Migrating to RTL ensures access to a vibrant ecosystem, community support, and ongoing improvements.
        d) Maintainability and Future-Proofing: Adapting to modern testing practices helps future-proof your codebase. By aligning with React Testing Library, you ensure compatibility with evolving React standards and frameworks, enhancing the maintainability of your test suite over time.
        e) Consistency Across Projects: Standardizing on React Testing Library promotes consistency across projects and teams. Developers familiar with RTL can seamlessly contribute to or maintain different projects that follow the same testing practices.
        f) Focus on User Behaviour: RTL encourages developers to focus on testing user interactions rather than implementation details. This shift not only results in more robust tests but also makes it easier to adapt to changes in the application's internal structure without breaking tests.

    2. Benefits of RTL over Enzyme:
        a) RTL promotes user-like interactions in component tests.
        b) Encourages interrogation of the DOM using text, roles and test id’s (e.g. there is no RTL method to get by class name as these are implementation details), we test what the user experiences when the page is rendered.
        c) Promotes stable and meaningful tests by hiding implementation details, whereas Enzyme allows access to component internals with methods like props().
        d) The syntax is clean and straightforward.
        e) Great documentation.
        f) Enzyme’s shallow render does not trigger React hooks such as useEfffect, so workarounds or other libraries are needed if you are using a functional component with hooks.
        g) An Enzyme react adapter allows compatibility with React 17 but support for future React versions looks uncertain.
    3. Prerequisites:
        a) @testing-library/react: is a very light-weight solution for testing React components.
        b) @testing-library/jest-dom: library provides a set of custom jest matchers that you can use to extend jest. These will make your tests more declarative, clear to read and to maintain.
        c) @testing-library/user-event: is a companion library for Testing Library that simulates user interactions by dispatching the events that would happen if the interaction took place in a browser.
           
    4. Installation:
       Note: React Testing Library versions 13+ require React v18. If your project uses an older version of React, be sure to install version 12
        a) To install dependencies run the following command:
           npm install –-save-dev @testing-library/react@12 @testing-library/jest-dom@latest @testing-library/user-event@latest
           
        b) Import @testing-library/jest-dom once in your tests setup file (i.e. src/setupTests.js file).
        c) Add these 
           
    5. Basic Concepts:
        a) Introduce developers to the basic concepts of React Testing Library.
        b) Explain the philosophy of "testing the way the user interacts with your application."
    6. Test Structure Changes:
        a) Highlight the differences in test structure between enzyme and React Testing Library.
        b) Emphasize the shift from component-centric testing to behavior-driven testing.
    7. Selectors and Queries:
        a) Explain the use of queries in React Testing Library to select elements.
        b) Compare and contrast with enzyme's selector strategies.
    8. DOM Interactions:
        a) Illustrate how to simulate user interactions using React Testing Library.
        b) Provide examples of common actions like clicking, typing, and form submissions.
    9. Assertions and Matchers:
        a) Show the differences in assertions and matchers between enzyme and React Testing Library.
        b) Provide examples of common assertions for component behavior.
    10. Snapshot Testing:
        a) If applicable, explain any changes or considerations for snapshot testing in React Testing Library.
    11. Testing Async Behavior:
        a) Cover testing asynchronous behavior using async/await or other React Testing Library utilities.
        b) Compare with enzyme's approach to async testing.
    12. Migrating Existing Tests:
        a) Provide guidance on migrating existing enzyme tests to React Testing Library.
        b) Include code examples and common patterns for the migration.
    13. Best Practices:
        a) Offer best practices for writing effective tests with React Testing Library.
        b) Highlight the importance of testing user interactions rather than implementation details.
    14. Troubleshooting:
        a) Address common issues or challenges developers might face during the migration.
        b) Provide solutions and workarounds for potential problems.
    15. Resources:
        a) Include links to relevant documentation, tutorials, and other resources that can help developers during and after the migration process.
    16. Conclusion:
        a) Summarize key points and encourage developers to embrace the new testing paradigm for improved test quality.
