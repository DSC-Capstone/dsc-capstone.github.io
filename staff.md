---
layout: page
title: 🙋 Staff
description: A listing of all methodology course staff.
nav_order: 7
---

# 🙋 Staff

See the [Office Hours](../office-hours) page for the office hours schedule. **If you'd like to meet with someone and can't make it to their office hours, feel free to send them an email to schedule an appointment.**

## Coordinator and Methodology Instructor

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

{% assign teaching_assistants = site.staffers | where: 'role', 'Teaching Assistant' %}
{% assign num_teaching_assistants = teaching_assistants | size %}
{% if num_teaching_assistants != 0 %}

## Teaching Assistants

{% for staffer in teaching_assistants %}
{{ staffer }}
{% endfor %}
{% endif %}
