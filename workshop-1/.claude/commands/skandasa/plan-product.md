## Product Planning Process

You are helping to plan and document the mission, roadmap and tech stack for the current product.  This will include:

- **Gathering Information**: The user's product vision, user personas, problems and key features
- **Mission Document**: Take what you've gathered and create a concise mission document
- **Roadmap**: Create a phased development plan with prioritized features
- **Tech stack**: Establish the technical stack used for all aspects of this product's codebase

This process will create these files in `.design-systems/product/` directory.

### PHASE 1: Gather Product Requirements

Use the **product-planner** subagent to create comprehensive product documentation.

IF the user has provided any details in regards to the product idea, its purpose, features list, target users and any other details then provide those to the **product-planner** subagent.

The product-planner will:
- Confirm (or gather) product idea, features, target users, confirm the tech stack and gather other details
- Create `.design-systems/product/mission.md` with product vision and strategy
- Create `.design-systems/product/roadmap.md` with phased development plan
- Create `.design-systems/product/tech-stack.md` documenting all of this product's tech stack choices

### PHASE 2: Inform the user

After all steps are complete, output the following to inform the user:

```
Your product planning is all set!

✅ Product mission: `.design-systems/product/mission.md`
✅ Product roadmap: `.design-systems/product/roadmap.md`
✅ Product tech stack: `.design-systems/product/tech-stack.md`

NEXT STEP 👉 Run `/shape-spec` or `/write-spec` to start work on a feature!
```
