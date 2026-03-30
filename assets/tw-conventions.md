# Taskwarrior → Notion → Quarto mapping
# Save as: ~/.task/quarto-conventions.md

## Project taxonomy

| project:              | Notion database    | Quarto path              |
|-----------------------|--------------------|--------------------------|
| schf                  | SCHF Hub           | quarto://schf/           |
| schf.people           | SCHF Hub           | quarto://schf/people/    |
| schf.research         | SCHF Hub           | quarto://schf/research/  |
| portfolio             | Academic Writing   | quarto://portfolio/      |
| courses               | Courses            | quarto://courses/        |
| courses.logic         | Courses            | quarto://courses/logic/  |
| courses.intro         | Courses            | quarto://courses/intro/  |
| courses.law           | Courses            | quarto://courses/law/    |
| courses.mind          | Courses            | quarto://courses/phil-mind/ |
| academic              | Academic Writing   | (paper-specific)         |

## Tag conventions

| tag          | meaning                              |
|--------------|--------------------------------------|
| +draft       | content in progress                  |
| +migrate     | needs moving from old site           |
| +syllabus    | syllabus-related task                |
| +week        | weekly lecture prep                  |
| +assignment  | assignment creation/grading          |
| +sync        | syncall / Notion sync issue          |
| +quarto      | Quarto render/build task             |
| +deploy      | GitHub Actions / deployment          |

## task annotate examples

# Link a task to a specific Quarto folder:
task <id> annotate "quarto://courses/logic/weeks/week03.qmd"

# Link to a Notion page (paste the Notion page URL):
task <id> annotate "https://www.notion.so/your-page-id"

# Link to both:
task <id> annotate "quarto://courses/intro/syllabus.qmd"
task <id> annotate "https://www.notion.so/your-courses-db-page-id"

## syncall ~/.syncall.yaml snippet

# tw_notion_sync section:
# taskwarrior_filter: "status:pending"
# notion_database_id: "<your-master-tasks-db-id>"
# tw_notion_property_map:
#   description:  Name
#   project:      Project
#   tags:         Tags
#   priority:     Priority
#   due:          Due
#   annotations:  QuartoLink   # first annotation → URL property in Notion
