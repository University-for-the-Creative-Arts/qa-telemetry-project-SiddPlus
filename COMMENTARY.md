This document outlines the technical approach used for collecting hybrid player data—both subjective feedback and self-reported quantitative metrics—for the Final Major Project (FMP). This strategy centered on a single, highly accessible input source: the Google Form survey, designed to efficiently gather both qualitative insights and essential performance context. This methodology provides a robust, data-informed foundation for Quality Assurance (QA) and subsequent game design iteration, despite the absence of low-level engine tracing.

## Player Feedback and Consent Collection

All player feedback, including qualitative comments, quantitative ratings, and system-specific data, was collected exclusively via a dedicated, external Google Form survey. The survey was made accessible via a dynamic QR code embedded directly within the game’s main menu screen. This design choice was crucial, enabling testers to seamlessly transition to a secondary mobile device to complete the survey without interrupting their primary game session. This approach significantly improved the completion rate and allowed testers to record observations precisely when they occurred.

Crucially, informed consent was made a mandatory, non-skippable requirement within the Google Form, serving as an ethical and auditable gatekeeping step. This ensured testers explicitly confirmed their agreement to the data collection policy before proceeding. The policy clearly defined: 1) the anonymous nature of all collected data, 2) the types of data being collected (self-reported metrics, questionnaire responses), 3) the exclusive use of this data for project improvement, and 4) the data retention policy. By using the Google Form as the single collection point for all input and consent, a transparent and compliant record was maintained.

## Self-Reported Performance Data Logged

Given the sole reliance on the Google Form for tester input, all recorded gameplay data was self-reported by the player. The survey was structured to extract high-value quantitative data essential for diagnosing issues:

System Specifications: Testers reported their CPU model, dedicated GPU information, and operating system version. This objective hardware data is crucial for analyzing compatibility and diagnosing hardware-specific performance bottlenecks.

Performance Estimates: The survey collected subjective performance metrics, specifically the average Framerate (FPS) observed during intense combat scenarios. While self-reported, this figure, when correlated with the corresponding system specifications, provides a strong indicator of where performance budget is being exceeded across different hardware tiers.

Gameplay Milestones: Data such as the highest round survived was recorded. This provides an objective measure of success, which can then be triangulated against ratings for difficulty and enjoyment to validate the intended difficulty curve.

This dataset provides the essential quantitative context needed to interpret the subjective qualitative feedback.

## Tools, Frameworks, and Services Used

The data collection pipeline utilizes one primary service and a custom delivery mechanism:

Qualitative Feedback and Self-Reported Metrics: Google Forms was selected for its universal accessibility, simplicity, and automated aggregation of data into Google Sheets. This served as the sole, highly effective endpoint for all tester input.

Delivery Mechanism: A custom HTML page was created to generate a dedicated, high-resolution QR code linking directly to the Google Form. This code was intended for seamless integration into the FMP’s main menu, facilitating immediate, friction-free access to the survey.

## Informing QA and Game Improvements

The collected hybrid data is instrumental in driving a data-informed approach to QA and subsequent game design iteration. The methodology hinges on the triangulation of qualitative feedback with the self-reported quantitative metrics (System Specs and FPS).

For instance, if the Forms report consistently cites a specific ability as "overpowered" (qualitative), designers can immediately look at the correlation with "highest round survived" (quantitative milestone) to validate the claim. More importantly for QA, if testers report high subjective dissatisfaction with "stability" or describe the game as "laggy," the QA team immediately cross-references this qualitative complaint with the tester's self-reported System Specifications and average FPS. If the performance complaints are prevalent even among testers using high-end hardware, this issue is flagged as a high-priority, non-hardware-specific optimization bottleneck, ensuring that QA efforts are directed at core engine or rendering issues rather than simple hardware incompatibility. This strategy ensures design changes are necessary, validated by measurable (though self-reported) performance data, and supported by player consensus
