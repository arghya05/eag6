# Cognitive Agent with MCP Drawing Capabilities

This project implements a cognitive agent with four layers: Perception, Memory, Decision-Making, and Action. The agent can create drawings using the MCP (Multi-Channel Protocol) client-server architecture.

## Architecture

The agent consists of four cognitive layers:

1. **Perception Layer**: Collects user preferences and processes input
2. **Memory Layer**: Stores and retrieves information
3. **Decision Layer**: Makes decisions based on perception and memory
4. **Action Layer**: Executes actions using the MCP client

## Requirements

- Python 3.8+
- pydantic 2.5.2

## Installation

1. Clone this repository
2. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

## Usage

### Starting the MCP Server

First, start the MCP server in a separate terminal:

```
python mcp_server.py
```

### Running the Agent

Then, run the agent in another terminal:

```
python main.py
```

The agent will:
1. Ask for your personal preferences (name, location, interests, etc.)
2. Create a drawing with text about cognitive layers
3. Adjust the drawing based on your preferences
4. Save the result as an SVG file

## Files

- `main.py`: Main entry point that configures and runs the agent
- `perception.py`: Perception layer for understanding user input
- `memory.py`: Memory layer for storing and retrieving information
- `decision.py`: Decision-making layer for planning actions
- `action.py`: Action layer for executing decisions
- `mcp_client.py`: Client for communicating with the MCP server
- `mcp_server.py`: Server for handling drawing requests

## How It Works

1. The agent collects user preferences through interactive prompts
2. It processes the drawing task request
3. It makes decisions based on the task and user preferences
4. It executes the drawing action using the MCP client
5. It stores the results in memory for future reference

## Customization

You can customize the agent by:
- Modifying the user preference collection in `perception.py`
- Adding new decision-making logic in `decision.py`
- Extending the action capabilities in `action.py`
- Enhancing the memory storage in `memory.py`

## Development Guide

When modifying this code, use the following prompt structure for ChatGPT assistance:

```
Role: You are an expert automation engineer specializing in UI automation and drawing applications.

CONTEXT MANAGEMENT:
Previous Steps: {previous_actions: []}
Current State: {app_state: {}, error_state: {}}
Iteration: {current_attempt: 1, max_attempts: 3}

OUTPUT FORMAT:
{
    "reasoning_phase": {
        "step_by_step_thoughts": [
            "1. [Reasoning Type: Analysis/Planning/Debug] Thought explanation",
            "2. [Reasoning Type: Logic/Calculation/Validation] Next thought"
        ],
        "assumptions_made": ["list of key assumptions"],
        "potential_risks": ["identified risks"]
    },
    "action_plan": {
        "tool_selection": {
            "chosen_tool": "tool_name",
            "reason": "explanation",
            "alternatives": ["backup options"]
        },
        "steps": [
            {
                "step_number": 1,
                "action": "description",
                "validation": "verification method",
                "fallback": "alternative approach"
            }
        ]
    },
    "verification": {
        "pre_checks": ["list of checks before action"],
        "post_checks": ["list of validations after action"],
        "success_criteria": ["measurable outcomes"]
    },
    "code_changes": {
        "file": "path/to/file",
        "modifications": [
            {
                "type": "modification_type",
                "location": "specific_area",
                "change": "detailed change",
                "reasoning": "explanation"
            }
        ]
    }
}

TASK REQUIREMENTS:
1. Seashore Automation Goals:
   - Create new image (512x384)
   - Draw rectangle
   - Add centered text "Hello from MCP Client!"

2. Step-by-Step Instructions:
   - BEFORE EACH STEP: Explain your reasoning
   - DURING EACH STEP: Document assumptions and risks
   - AFTER EACH STEP: Verify success criteria

3. Tool Usage Rules:
   pyautogui:
   - Always specify exact coordinates
   - Include timing between actions
   - Validate mouse positions
   
   AppleScript:
   - Check window state
   - Verify application focus
   - Handle permissions
   
   Keyboard Shortcuts:
   - Document each shortcut
   - Verify key state
   - Include fallbacks

VERIFICATION REQUIREMENTS:
Before each action:
- [ ] Validate current application state
- [ ] Check tool availability
- [ ] Verify coordinates are safe

After each action:
- [ ] Confirm expected outcome
- [ ] Log success/failure
- [ ] Update context for next step

ERROR HANDLING PROTOCOL:
If error occurs:
1. Identify error type [UI/Tool/Logic]
2. Log detailed error state
3. Execute fallback strategy:
   - Retry with delays
   - Alternative method
   - Safe abort procedure

CONVERSATION LOOP:
1. State current understanding
2. Propose solution
3. Wait for confirmation
4. Execute or adjust based on feedback
5. Update context with results

REASONING TYPES TO TAG:
- [Analysis] For examining current state
- [Planning] For action sequencing
- [Logic] For decision making
- [Validation] For checking results
- [Debug] For error handling
- [Optimization] For improvements

Think through each step carefully and validate all assumptions. Explain your reasoning process explicitly before taking any action.

ENVIRONMENT:
- macOS (darwin 23.5.0)
- Python 3
- Seashore app

## Prompt Evaluation Results

The development prompt has been evaluated with the following results:

```json
{
  "explicit_reasoning": true,
  "structured_output": true,
  "tool_separation": true,
  "conversation_loop": true,
  "instructional_framing": true,
  "internal_self_checks": true,
  "reasoning_type_awareness": true,
  "fallbacks": true,
  "overall_clarity": "Excellent structure with clear reasoning steps, verification, and error handling."
}
```

## Key Components

### MCP Server (`mcp_server.py`)
- Manages application state
- Handles window positioning
- Provides status information

### Drawing Agent (`mcp_drawing_agent.py`)
- Implements drawing operations
- Handles UI automation
- Manages error handling and retries

### Client (`mcp_client.py`)
- Initiates drawing operations
- Communicates with server
- Handles user interaction

## Troubleshooting

Common issues and solutions:

1. Rectangle Drawing Issues:
   - Ensure Seashore is properly focused
   - Check mouse button parameters
   - Verify coordinate calculations

2. Text Entry Problems:
   - Confirm text tool selection
   - Check text positioning
   - Verify typing intervals

3. Window Management:
   - Ensure proper AppleScript execution
   - Verify window positioning
   - Check focus handling

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License - See LICENSE file for details

## Support

For issues and feature requests, please use the GitHub issue tracker. 