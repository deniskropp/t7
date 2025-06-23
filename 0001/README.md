# Unexpected Visitors: Narrative Scenes and Data

This repository contains structured data representing narrative scenes focused on the theme of unexpected and overstaying houseguests, and the resulting social dynamics and conflicts. The data is designed for potential use in applications like automated scene generation, interactive storytelling, script analysis, or training AI models for narrative understanding and generation.

## Project Overview

The project consists of a collection of scenes detailing different scenarios where hosts are faced with guests who extend their welcome beyond the initial agreement. Each scene includes character information, location, a plot summary, a dialogue goal, dialogue lines with associated actions, character positions, and camera/director shot selections.

The scenarios covered include:
1.  **Rex and Sarah hosting Luna:** A meticulously organized couple deals with a free-spirited cousin whose "weekend visit" extends indefinitely, leading to chaos and a difficult confrontation.
2.  **Leo hosting Sarah and Maya:** A minimalist host's quiet life is disrupted by distant cousins who arrive with excessive luggage and plans for a long-term stay, taking over his space.
3.  **Arthur hosting Finn and Luna:** A graphic designer's routine is shattered by a college friend and his girlfriend whose "weekend catch-up" turns into a two-week intrusion, culminating in a demand for them to leave.

## File Structure

The data is organized into JSON files within the `0001/` directory.

*   `0001/actors_profile.json`: Contains detailed profiles for a subset of characters, including age, gender, occupation, personality traits, and speaking style.
*   `0001/scenes_1.json` through `0001/scenes_8.json`: These files contain the core scene data. Note that some files (`scenes_6.json`, `scenes_7.json`, `scenes_8.json`) include character actions, current positions, and shot selections embedded within the dialogue entries, while others (`scenes_1.json` through `scenes_5.json`) contain only basic scene information, initial positions, and dialogues.
*   `0001/cinematographer_shot.json`: Contains cinematographer's shot selections, potentially representing a separate layer of annotation or a different version of scene data.
*   `0001/director_shot.json`: Contains director's shot selections, similar to the cinematographer file, suggesting different perspectives or iterations of shot planning.
*   `0001/script/0.json`: Another scene data file, following a similar structure to `scenes_6/7/8.json` with embedded actions, positions, and shots.

## Data Structure

The primary data structure is a JSON array of scene objects. Each scene object generally contains:

*   `sceneinformation`:
    *   `who`: An array of character names present in the scene.
    *   `where`: The location of the scene.
    *   `what`: A summary of the scene's plot and context.
*   `initial position`: An array specifying the starting position for each character using abstract position identifiers (e.g., "Position 1", "Position 2").
*   `dialogues`: An array of dialogue entries. Each entry represents a line spoken by a character or a character action.
    *   `speaker`: The name of the character speaking (or performing an action if no content).
    *   `content`: The dialogue text (optional for action-only entries).
    *   `actions`: An array of actions performed by characters during or immediately after this dialogue line. Each action includes:
        *   `character`: The character performing the action.
        *   `state`: The physical state of the character (e.g., "standing", "sitting").
        *   `action`: The specific action performed (e.g., "Standing Talking", "Sitting Happy", "Standing Surprise", "Sit Down", "Stand Up").
        *   `reason`: A brief explanation for the action choice.
    *   `current position`: (Present in some files) An array showing the position of each character *after* this dialogue/action entry.
    *   `selected shot`: (Present in some files) The chosen camera shot for this moment (e.g., "Close Shot", "Mid Shot", "Pan Shot").
    *   `move`: (Present in some files) An object indicating a character movement, including:
        *   `character`: The character moving.
        *   `destination`: The target position.
        *   `reason`: Explanation for the movement.
        *   `insertion`: Details about where this movement action is inserted in the sequence.

## Characters

The `actors_profile.json` file provides details for the following characters:

*   **Sarah:** Introverted, meticulously organized librarian. Soft-spoken and precise.
*   **Leo:** Charismatic, free-spirited wandering musician. Expressive and theatrical.
*   **Maya:** Earthy, overly spiritual holistic healer. Calming but uses jargon.

*Note: Other characters like Rex, Luna, Arthur, and Finn appear in the scene files but do not have corresponding entries in the provided `actors_profile.json`.*

## Usage and Interpretation

This data can be used to:

*   Visualize scenes: Interpret positions, states, and actions to create visual representations of the characters and their movements.
*   Generate animations: Use the sequence of dialogues, actions, and movements to drive character animation.
*   Analyze narrative flow: Study the progression of conflict and character states across scenes.
*   Develop interactive stories: Use the dialogue and action structure as the basis for branching narratives or character interactions.
*   Train machine learning models: Use the structured data to train models for generating narrative scenes, predicting character actions, or selecting camera shots based on dialogue and context.

The different versions of scene files (with and without embedded actions/shots) and the separate shot files (`cinematographer_shot.json`, `director_shot.json`) suggest potential variations or stages in a production pipeline, where core dialogue is first drafted, then actions, positions, and shots are added or planned.

## Potential Applications

*   Automated comic strip or storyboard generation.
*   AI-driven scriptwriting assistants.
*   Educational tools for film studies or creative writing.
*   Character behavior simulation.

## License

[Specify your desired license here, e.g., MIT, Apache 2.0, Creative Commons, or state "All Rights Reserved"]

## Credits

[Add author or project credits here]
