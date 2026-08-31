# UI Forge

AI Roblox UI Builder — Full Development Prompt

Create a professional AI-powered Roblox UI Builder that acts as a WRAPPER around Roblox Studio's UI workflow.

This is not a replacement for Roblox Studio. It is an AI-assisted visual UI design tool that makes creating Roblox interfaces much easier. A Roblox Studio plugin should act as the bridge between the wrapper and the user's actual Roblox Studio project.

The user should be able to create UI through AI, visually edit every element, import screenshots and have them reconstructed into editable Roblox UI, automatically optimise the UI for different screen sizes, and then send the finished result directly into Roblox Studio.

The core workflow should be:

Prompt / Upload → AI generates UI → Edit visually → Properties → Auto-scale → Preview → Send to Roblox Studio

1. Wrapper Architecture

The application must clearly be designed as a wrapper around Roblox Studio, specifically around the Roblox UI creation workflow.

Do not attempt to recreate all of Roblox Studio.

Only recreate the functionality needed for UI design, including:

 Explorer

 Properties

 UI canvas

 UI hierarchy

 UI object editing

 Asset management

 AI generation

 Image-to-UI generation

 Responsive scaling

 Device previews

 UI validation

 Roblox Studio synchronisation

Roblox Studio remains the actual development environment and source of the final Roblox project.

The wrapper should communicate with Roblox Studio through a dedicated Roblox Studio plugin.

2. Main Purpose

The tool should allow users to create Roblox UI without needing to manually construct every Frame, TextButton, ImageLabel, constraint, layout and styling object themselves.

The user should be able to say:

"Create a modern simulator UI with a currency display at the top, a large play button in the centre, and shop and inventory buttons at the bottom."

The AI should create the complete visual UI and hierarchy.

The user can then manually edit anything using the canvas and Properties panel.

3. Layer-Based UI System

Every UI object must be represented as an individual layer.

For example:

 ScreenGui

 Background

 TopBar

 Currency

 Icon

 Amount

 SettingsButton

 PlayButton

 ShopButton

 InventoryButton

Each layer must be independently:

 Selected

 Moved

 Resized

 Rotated

 Renamed

 Duplicated

 Deleted

 Hidden

 Locked

 Reordered

 Re-parented

 Styled

 Edited through Properties

The layer hierarchy should represent the actual Roblox UI hierarchy.

If an object is moved to another parent, the underlying Roblox hierarchy should update accordingly.

4. Explorer and Properties

The Explorer and Properties must be in the SAME panel/tab.

Do not make them separate tabs.

The Explorer must be above the Properties panel, just like the Roblox Studio workflow.

There should be a draggable divider between them so users can adjust how much space each section receives.

The Explorer should display the complete UI hierarchy.

Selecting an object in Explorer should select it on the canvas and display its properties below.

Selecting an object on the canvas should automatically select and highlight the corresponding object in Explorer.

The two sections should stay synchronised at all times.

5. Roblox Studio-Style Explorer

The Explorer should visually and functionally resemble Roblox Studio's Explorer.

It should include:

 Hierarchy indentation

 Expand/collapse arrows

 Object icons

 Object names

 Selection highlighting

 Search

 Drag-and-drop hierarchy editing

 Visibility controls

 Lock controls

Support right-click context menus containing options such as:

 Rename

 Duplicate

 Delete

 Copy

 Paste

 Group

 Ungroup

 Move to Front

 Move Forward

 Move Backward

 Move to Back

 Hide

 Lock

 Copy Style

 Paste Style

 Rename with AI

 Explain with AI

 Generate Children

 Convert to Component

6. Roblox Studio-Style Properties

The Properties section underneath Explorer should closely resemble the Roblox Studio Properties panel.

Properties should be organised into expandable categories.

The properties shown should dynamically change depending on the selected Roblox UI object.

For a Frame, support properties such as:

Appearance

 BackgroundColor3

 BackgroundTransparency

 BorderColor3

 BorderMode

 BorderSizePixel

 Visible

Data

 Name

 Parent

 ClassName

Layout

 AnchorPoint

 Position

 Rotation

 Size

 ZIndex

Behaviour

 Active

 Selectable

UI

 ClipsDescendants

 AutomaticSize

Also support relevant Roblox UI objects and their properties.

For TextLabel and TextButton, include:

 Text

 Font

 TextSize

 TextColor3

 TextTransparency

 TextStrokeColor3

 TextStrokeTransparency

 TextWrapped

 TextScaled

 TextXAlignment

 TextYAlignment

 RichText

 LineHeight

 MaxVisibleGraphemes

For ImageLabel and ImageButton, include:

 Image

 ImageColor3

 ImageTransparency

 ScaleType

 SliceCenter

 SliceScale

 TileSize

 ResampleMode

For UIStroke, include:

 Color

 Thickness

 Transparency

 ApplyStrokeMode

 LineJoinMode

For UIGradient, include:

 Color

 Transparency

 Rotation

 Offset

Properties must update the canvas instantly.

7. Supported Roblox UI Objects

Support the major Roblox UI instances, including:

 ScreenGui

 Frame

 ScrollingFrame

 TextLabel

 TextButton

 ImageLabel

 ImageButton

 ViewportFrame

 CanvasGroup

Support UI objects and modifiers such as:

 UICorner

 UIStroke

 UIGradient

 UIPadding

 UIListLayout

 UIGridLayout

 UIPageLayout

 UIAspectRatioConstraint

 UIScale

 UISizeConstraint

 UITextSizeConstraint

The AI should automatically select appropriate Roblox objects based on what the user is trying to create.

8. Visual Canvas

The centre of the application should contain the main UI canvas.

The canvas should represent the UI as accurately as possible.

Users should be able to:

 Click elements

 Drag elements

 Resize elements

 Rotate elements

 Duplicate elements

 Delete elements

 Multi-select

 Align elements

 Distribute elements

 Group elements

 Zoom

 Pan

Selected objects should display bounding boxes and resize handles.

Canvas changes must update the Properties panel.

Properties changes must update the canvas.

9. Import Your Own Images

Include an Import Image feature that allows users to upload their own images.

Support common formats such as:

 PNG

 JPG

 JPEG

 WebP where appropriate

Users should be able to import:

 Roblox UI screenshots

 UI mockups

 Game interface references

 Existing designs

 Their own artwork

 Icons

 Backgrounds

 Individual UI assets

The AI should be able to analyse an uploaded image and understand its visual structure.

10. Image-to-UI AI Reconstruction

This is one of the most important features.

When a user uploads a screenshot of a UI, do not simply place the screenshot into an ImageLabel and call it finished.

Instead, use the image as a reference and reconstruct the interface using editable Roblox UI objects.

The AI should identify things such as:

 Frames

 Buttons

 Text

 Icons

 Images

 Backgrounds

 Borders

 Rounded corners

 Gradients

 Shadows

 Spacing

 Alignment

 Relative sizes

 Colours

 UI hierarchy

For example, a screenshot containing a currency display should be reconstructed into separate elements such as:

 CurrencyFrame

 CurrencyIcon

 CurrencyText

A button should be reconstructed into its appropriate editable elements rather than remaining a single screenshot.

The user must be able to select every detected element individually after generation.

11. AI Image Analysis

After an image is imported, show an analysis stage.

The AI should identify how many elements it has detected and what types they are.

For example:

 Background detected

 Frames detected

 Buttons detected

 Text detected

 Icons detected

 Decorative elements detected

Provide options such as:

Accurate Recreation

and

Recreate + Improve

Accurate Recreation should prioritise matching the reference.

Recreate + Improve should preserve the original design while making it cleaner, more consistent and more suitable for Roblox.

12. Asset Management

Create an Assets section for imported visual assets.

Users should be able to manage:

 Icons

 Backgrounds

 Images

 UI artwork

 Decorative assets

Assets should be reusable.

Users should be able to drag an asset onto the canvas.

The AI should determine whether an asset should become:

 ImageLabel

 ImageButton

 Background

 Icon

 Decorative element

Images should remain actual visual assets rather than being converted into code.

13. AI Prompt System

Include an AI command/prompt box.

Users should be able to describe what they want to create or change using natural language.

Examples:

Create a clean simulator UI.

Add a currency counter to the top right.

Make this button larger.

Move the inventory button to the bottom right.

Make every button match the Shop button.

Change the colour scheme to blue and white.

Make this look more futuristic.

Recreate this uploaded image.

Make the UI work better on mobile.

Add a settings menu.

Make the interface more polished.

Add rounded corners to all buttons.

Make the top bar smaller.

The AI should directly modify the visual layer structure.

It should not simply respond with instructions.

14. AI Context Awareness

The AI should understand the current UI hierarchy.

If the user selects a particular object and says:

"Make this bigger."

the AI should modify the selected object rather than creating a new one.

If the user selects a button and says:

"Use this style for all buttons."

the AI should identify other buttons and apply the same design.

The AI should understand:

 Current selection

 Layer hierarchy

 Existing assets

 Existing styles

 Current device preview

 Current properties

 Existing components

15. Design System

The builder should maintain a consistent design system throughout the project.

Automatically recognise and reuse:

 Colours

 Gradients

 Corner radii

 Font choices

 Text sizes

 Stroke styles

 Shadows

 Spacing

 Button designs

 Panel designs

 Icon styles

If the user creates a button style, the AI should be able to apply it consistently to other buttons.

16. Automatic Responsive Scaling

The UI must automatically scale correctly across different screen sizes.

This is a core requirement.

Do not create UI that only looks correct at one fixed resolution.

The AI should intelligently use:

 UDim2 Scale

 AnchorPoint

 UIAspectRatioConstraint

 UIScale

 UIListLayout

 UIGridLayout

 UIPadding

 AutomaticSize

 UISizeConstraint

 Relative positioning

Avoid unnecessary fixed pixel offsets.

When reconstructing an image, analyse the proportions of the reference and convert them into appropriate Roblox scale-based positioning and sizing.

The resulting UI should adapt to different resolutions and aspect ratios.

17. Automatic Mobile Optimisation

The AI should automatically optimise the UI for mobile.

Consider:

 Touch target size

 Button spacing

 Text readability

 Safe areas

 Screen proportions

 Overlapping elements

 Layout rearrangement

The user should be able to say:

"Optimise this for mobile."

The AI should automatically adjust the design while maintaining the original visual style.

18. Device Preview

Include device preview options for:

 PC

 Laptop

 Mobile

 Tablet

 Console

Allow users to change the preview resolution and aspect ratio.

The canvas should update to represent the selected device.

The user should be able to quickly test whether their UI remains usable across different screen sizes.

19. Automatic UI Validation

Before exporting, analyse the UI for potential issues.

Detect things such as:

 Overlapping elements

 Text being too small

 Buttons being too small for mobile

 Fixed offsets

 Incorrect scaling

 Stretched images

 Incorrect aspect ratios

 Elements outside the safe area

 Broken hierarchy

 Missing constraints

Display warnings and provide:

Fix with AI

The AI should automatically correct safe layout problems without unnecessarily changing the user's design.

20. Components

Allow groups of UI layers to be saved as reusable components.

For example, a complete button could become a reusable:

ButtonComponent

containing:

 Background

 Icon

 Text

 UICorner

 UIStroke

 UIGradient

Users should be able to reuse components throughout the project.

Allow optional component syncing so that modifying the original component can update its instances.

21. Animation Support

Allow users to add basic UI animations such as:

 Hover

 Click

 Open

 Close

 Fade

 Slide

 Scale

 Bounce

 Rotate

Users should be able to ask the AI:

Make the button grow slightly when hovered.

or:

Make this menu slide in from the right.

The AI should configure the necessary Roblox UI behaviour through the plugin/workflow.

22. Preview Mode

Provide a Preview mode that removes the editor controls and displays the UI as the player would see it.

The preview should use the actual generated UI hierarchy.

Allow users to test:

 PC

 Mobile

 Tablet

 Console

The preview should reflect responsive scaling.

23. Roblox Studio Plugin

Create a dedicated Roblox Studio plugin that acts as the bridge between the wrapper and the user's Roblox Studio project.

The plugin should be lightweight and focused on:

 Connecting the wrapper

 Sending UI data

 Importing UI

 Updating existing UI

 Creating Roblox instances

 Synchronising changes

The plugin should allow the user to connect their Roblox Studio project to the wrapper.

24. Send UI to Roblox Studio

Provide a prominent:

Send to Roblox Studio

function.

When used, the plugin should create the actual Roblox UI instances inside the user's project.

The resulting hierarchy should appear inside:

StarterGui

and match the layer hierarchy created in the wrapper.

For example:

 ScreenGui

 MainFrame

 TopBar

 Currency

 PlayButton

 ShopButton

 InventoryButton

The plugin must create actual Roblox instances, not a screenshot.

25. Preserve UI Properties

When sending the UI to Roblox Studio, preserve all relevant information, including:

 Hierarchy

 Names

 Parent relationships

 Position

 Size

 AnchorPoint

 Rotation

 ZIndex

 Colours

 Transparency

 Fonts

 Text

 Images

 Gradients

 Strokes

 Corners

 Padding

 Layouts

 Constraints

 Aspect ratios

 Responsive scaling

The UI in Roblox Studio should visually match the wrapper's preview as closely as possible.

26. Two-Way Synchronisation

Support synchronisation between the wrapper and Roblox Studio where possible.

The workflow should support:

Send to Studio

Update Existing UI

Import from Studio

Sync Changes

The user should not have to create duplicate UI every time they make an update.

If an existing UI was previously sent to Roblox Studio, the plugin should recognise it and update it rather than unnecessarily creating another copy.

27. Roblox Studio Remains the Final Environment

The wrapper should never pretend to replace Roblox Studio.

After exporting/syncing, the user can continue working normally in Roblox Studio.

The wrapper is simply an AI-powered UI design and editing layer that makes the UI creation process faster.

Roblox Studio remains responsible for the actual Roblox development environment.

28. No-Code UI Workflow

The normal user experience should require no Lua knowledge.

The user should interact primarily with:

 Canvas

 Explorer

 Properties

 Assets

 AI prompts

 Device previews

 Components

The underlying system can generate whatever data or plugin instructions are required, but the user should not have to manually write code.

Do not make a code editor the primary part of the application.

29. Undo / Redo

Support full undo and redo.

Every AI operation should be reversible.

For example:

 AI creates UI

 User changes colour

 AI resizes buttons

 User moves a frame

 AI optimises mobile

The user should be able to undo each action individually.

30. Version History

Include project version history.

Save major versions automatically.

Users should be able to see previous versions and restore them.

Examples of version descriptions:

 Initial UI

 Added Shop

 Redesigned Buttons

 Added Mobile Support

 AI Optimisation

 Final UI

31. Export System

The main export system should focus on the Roblox Studio plugin.

Options should include:

 Send to Roblox Studio

 Update Existing UI

 Import from Studio

 Sync

 Export Project

 Export Assets

The primary workflow should be:

Send to Roblox Studio

rather than requiring the user to manually copy Lua scripts.

32. Important Design Rules

Follow these rules throughout the entire application:

 This application is a WRAPPER around Roblox Studio, not a replacement for Roblox Studio.

 Focus only on the Roblox UI creation workflow.

 Explorer and Properties must be in the same panel.

 Properties must be underneath Explorer.

 The Explorer should feel like Roblox Studio's Explorer.

 The Properties panel should feel like Roblox Studio's Properties panel.

 Every UI element must be an individual editable layer.

 The canvas must visually represent the actual UI hierarchy.

 Imported screenshots must be reconstructed into editable UI rather than simply becoming one ImageLabel.

 Users must be able to import their own images and assets.

 AI must be able to generate and modify UI using natural language.

 The UI must automatically scale responsively.

 Prefer Scale, AnchorPoint and Roblox UI constraints over unnecessary fixed offsets.

 Support PC, mobile, tablet and console previews.

 AI should automatically detect and fix responsive layout problems.

 The Roblox Studio plugin must create actual Roblox UI instances.

 The generated hierarchy must match the wrapper's layer hierarchy.

 Preserve all relevant Roblox UI properties when syncing.

 Users should not need to write Lua for normal UI creation.

 Support undo and redo for all major actions.

 Maintain consistent design systems across the project.

 Keep Roblox Studio as the actual final development environment.

 The plugin should synchronise the wrapper with the user's real Roblox project.

 Do not make the application look like a generic website builder — it should feel purpose-built for Roblox UI creation.

33. Final Goal

The finished product should essentially be:

An AI-powered visual wrapper for Roblox Studio's UI workflow.

A user should be able to take a UI screenshot, upload it, let AI analyse it, have the AI rebuild it as individual editable Roblox UI layers, modify everything through a Roblox Studio-style Explorer and Properties panel, automatically scale it for different devices, preview it, and then send the finished UI directly into Roblox Studio using the plugin.

The key experience should be:

Upload → AI Recreates → Edit → Properties → Auto-Scale → Preview → Sync → Roblox Studio.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/807107cc-c868-484a-ad6a-b81347c5f7ca).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
