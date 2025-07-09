---
title: "SmartLink Examples"
description: "Real, working examples of hugo-smartlink. No fake features or links."
date: 2024-07-09
draft: false
---

# SmartLink Examples

아래 예제들은 모두 실제로 hugo-smartlink에서 동작하는 예시입니다.

## WikiLink
- `[[examples]]` → `/examples`
- `[[documentation|Read the docs]]` → `/documentation` (라벨 지정)

## JIRA Issue
- `[[PROJ-123]]` → `https://company.atlassian.net/browse/PROJ-123`

## GitHub Issue
- `[[#42]]` → `https://github.com/qgp9/hugo-smartlink/issues/42`

## Slack Channel
- `[[slack:#general]]` → `https://company.slack.com/app_redirect?channel=general`

## Email Link
- `[[email:contact@example.com]]` → `mailto:contact@example.com`

## Prefix Alias
- `[[docs:installation]]` → `/documentation/installation`

---

*위 예시 외의 기능, 옵션, 링크는 실제로 동작하지 않으므로 문서에 포함하지 않습니다.* 