# Elevenlabs-s2s

This is an example Jambonz application that connects to the Elevenlabs Realtime API and illustrates how to build a Voice-AI application using Jambonz and Elevenlabs. This application utilizes a weather REST API to enable Elevenlabs to answer callers' questions about the weather for specified locations.

## Authentication
To use this application, you'll need an Elevenlabs Agent ID that has access to the Realtime API. Set the Agent ID as an environment variable before launching the application, like so:

```bash
ELEVENLABS_AGENT_ID=<agent_id> npm start
```

Replace `<agent_id>` with your actual Elevenlabs Agent ID.

> Note: If you're using a private agent, you must also set the ELEVENLABS_API_KEY environment variable when starting the application.

## Prerequisites
This application requires a Jambonz server running release `0.9.2-rc3` or above.

## Configuring the Assistant
Elevenlabs requires the assistant to be configured before connecting to the agent. This application uses the `llm` verb with `llmOptions` to send the initial configuration to Elevenlabs. For details, refer to the Elevenlabs documentation: [Elevenlabs Agent Setup](https://elevenlabs.io/docs/conversational-ai/docs/agent-setup).

## Client tools
[Elevenlabs client tools](https://elevenlabs.io/docs/conversational-ai/customization/client-tools), setup a tool with promt to get weather

## ActionHook
Like many Jambonz verbs, the `llm` verb sends an `actionHook` with a final status when the verb completes. The payload includes a `completion_reason` property indicating why the `llm` session ended. Possible values for `completion_reason` are:

- Normal conversation end
- Connection failure
- Disconnect from remote end
- Server failure
- Server error

---

Ensure all environment variables are properly configured before starting the application. For detailed API references and documentation, visit the [Elevenlabs Documentation](https://elevenlabs.io/docs/conversational-ai/api-reference/conversational-ai/websocket).

