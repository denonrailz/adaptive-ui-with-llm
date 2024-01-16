Denis Shuleikin
December 2023
den.on.rails@gmail.com

# Abstract
Chatbots have become increasingly popular among everyday users, leading to their use not only for acquiring new knowledge but also for analytics, research, and machine interaction (computers). In this context, a chat interface alone is often insufficient. This concept aims to describe new types of user interfaces (UI) based on chat with Large Language Model (LLM) agents. An adaptive UI, integrating the chat interface of an LLM agent with familiar UI components, enhances the user experience. While interacting with a chatbot like ChatGPT, users will receive not just text-based answers but also a dashboard that enriches the response with links, images, statistical data, and other UI components commonly used in operating systems, applications, and websites. A graphical representation of LLM responses will facilitate easier understanding and deeper user engagement. Based on provided layout grids and examples, the LLM agent will generate a new layout each time it provides a chat response.

# Background and Problem Statement
LLM chats (AI agents) gained significant popularity in 2023, with many people using them for various tasks. However, interactions based solely on text chats with text or image outputs are often limited in utility. As LLM agents (chats) become widely adopted, there is a growing need for more adaptive and familiar UIs. Current interfaces in operating systems like iOS, Android, Windows, and MacOS are more familiar and offer greater interaction speed. For instance, when asking an LLM about your contact list, you might expect something akin to an address book with familiar UX features (scrolling, detail viewing, etc.), rather than just a list. Thus, combining the chat interface with UI/UX components could create a new generation of UI/UX, harnessing the best of both worlds: the ease of interaction with UI components and the flexibility of chat interaction. When sending requests to a human-computer interface, users expect a familiar response. Text-based interaction requires more human involvement. Companies producing AI IoT devices will also face this challenge. This document defines the concept of new hybrid chat/UI interfaces for the next generation of LLM applications.

# Concept Overview
The UI consists of chat history and a dynamically generated UI based on chat context. The generated UI could be an interactive dashboard augmenting the LLM response, with the ability to interact with it. Links to extended data, shortcuts, summaries, or even control panel elements could be generated in response to user queries.

![[concept01.png]]*Fig. 1. Example of an adaptive UI response from a chatbot

The discussion begins with a text or voice

input to the LLM. The UI LLM agent then provides a layout that users can interact with, similar to a regular UI. A key feature is that this UI can adapt to user needs or habits. Users can customize the UI through prompts, followed by regular interactions similar to those in current CRMs, ERPs, etc.

### Dynamic UI for Regular Apps
One use case could involve a standard UI at the start, with the option to customize it through text or voice prompts. For example, a user sees a regular CRM dashboard, then opens a UI customization chat and requests to rebuild it based on their needs. The UI LLM agent then reconstructs the dashboard layout and saves it for future use. A prompts marketplace (library) could be a list of prompts for application customization.

#### How Will This UI Be Built?
In this scenario, UI developers would provide a layout grid and tag it appropriately. They would then provide examples (train the LLM) of using this layout as extensively as possible. This allows the LLM agent to independently generate a UI based on designer guidelines and user needs.

## Design Principles
Based on application-specific requirements, the UI designer provides a layout grid, components, a JSON schema, and examples.

#### Components
Each element of the UI grid is a defined component. For example:

> **Block with Number**: A header of 3 to 15 symbols. A number less than 10 digits, and a short (less than 30 symbols) description. This component is used for displaying important numbers.

After defining each element, we establish a JSON schema for configuring each component. As a result, we can define a JSON that can be implemented as HTML blocks.

#### Grid System
Based on the components, the design provides grid layout examples that define system limitations – what can and cannot be done. It also defines behavior at different resolutions, for

example. Like the components, the grid system can also be specified in a machine-readable format (such as JSON). Thus, we can define the grid by providing a valid JSON schema.

#### Examples
With the 'bricks' of components and the 'rulers' of the grid in place, the designer will provide examples of how to use the system. Each example should come with a description of its use cases. For example:
> "This layout displays extended sales statistics for a manager. Use it if a user asks about salesperson details."

#### Generation
Having a JSON-defined grid and component system, supplemented with examples, our LLM can generate JSON that will represent the future design. A UI interpreter can then transform this JSON into HTML to be rendered for the user. This process allows for dynamic, user-responsive UI design that can adapt to various needs and preferences, enhancing the overall user experience with LLM-based applications.