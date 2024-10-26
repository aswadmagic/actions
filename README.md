# Create Billing Server Tag Workflow

This GitHub Actions workflow automates the process of creating and pushing a new tag for the Billing Server image.

## Workflow Description

The "Create Billing Server Tag" workflow is designed to:

1. Validate the format of the provided tag name.
2. Check if the tag already exists.
3. Create and push a new annotated tag if it doesn't exist.

## Advantages

Using this automated workflow provides several benefits:

1. **Consistency**: Ensures that all tags follow the required naming convention.
2. **Error Prevention**: Prevents accidental overwriting of existing tags.
3. **Efficiency**: Saves time by automating the tag creation and push process.
4. **Traceability**: Creates annotated tags with descriptions, improving version tracking.
5. **Accessibility**: Allows team members to create tags without direct repository access.
6. **Integration**: Fits seamlessly into your CI/CD pipeline.
7. **Auditability**: All tag creations are logged in GitHub Actions, providing a clear audit trail.

## Usage

This workflow is triggered manually using the `workflow_dispatch` event. To use it:

1. Go to the "Actions" tab in your GitHub repository.
2. Select the "Create Billing Server Tag" workflow.
3. Click on "Run workflow".
4. Fill in the required inputs:
   - **Tag name**: Must be in the format `billing-server-img/vX.Y.Z` (e.g., `billing-server-img/v1.2.3`)
   - **Tag description**: A brief description of the tag or the changes it represents

## Workflow Details

### Inputs

- `tag_name`: The name of the tag to create (required)
- `tag_description`: A description for the tag (required)

### Steps

1. **Checkout repository**: Fetches the repository content.
2. **Validate tag name**: Ensures the tag name follows the required format.
3. **Check if tag already exists**: Prevents overwriting existing tags.
4. **Create and push tag**: Creates an annotated tag and pushes it to the repository.

### Permissions

This workflow requires the following permissions:

- `contents: write`: To create and push tags
- `actions: write`: To run the workflow

## Error Handling

The workflow will fail if:

- The tag name doesn't match the required format.
- The specified tag already exists in the repository.
