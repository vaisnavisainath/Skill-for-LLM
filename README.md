# Global Opportunity Navigator

## Project Overview

Global Opportunity Navigator is a modular LLM skill that helps students and early career researchers in the humanities and social sciences find, filter, rank, and apply to global opportunities. These include PhD programs, scholarships, fellowships, visiting research positions, archive grants, summer schools, exchange programs, internships, and jobs.

## Objectives

- Build a clear profile of the applicant.
- Search current official sources for opportunities.
- Filter out opportunities the applicant is not eligible for.
- Rank the rest by fit, funding, research value, competitiveness, and time left.
- Verify every deadline, amount, and link.
- Produce a dated action plan and, on request, application material.

## Modules

1. Profile Module
2. Discovery Module
3. Filter Module
4. Ranking Module
5. Verification Module
6. Action Plan Module
7. Application Support Module
8. Output Module

## Configurable Switches

- Fully funded only
- Open deadlines only
- Strict source verification
- Include programmes with application fees
- Include rolling deadlines
- Balanced reach, target, and safe mix

## Technologies

- Markdown
- JSON
- HTML
- JavaScript
- GitHub

## Example Queries

- Find fully funded PhD programs in cultural studies or sociology abroad.
- Which fellowships can an Indian humanities researcher apply for to visit an archive overseas?
- Make a month by month plan for applying to PhD programs in Europe, including the writing sample and research proposal.
- Am I eligible for this scholarship, and what is the deadline?

## Project Structure

global-opportunity-navigator/
- SKILL.md
- references/
- config/
- examples/
- index.html
- README.md

## Usage

SKILL.md holds the main instructions. The files in references/ hold the individual modules. config/switches.json defines module activation and the six switches. index.html is a small website that builds a settings file for you to give to the skill.

An LLM application with skill loading and web search is required to run the full workflow. Without web search the skill can only give unverified leads with official URLs.

## Limits

The skill does not give visa or legal advice, does not guarantee selection, and does not predict admission outcomes. Always confirm deadlines and eligibility on the official page before applying.

## Author

Prajesh Anand
Prepared for Vaisnavi Sainath
Department of Humanities and Social Sciences, IIT (ISM) Dhanbad
Monsoon Semester 2026
