# Project Brief

## Project Name

VitaClaw FDE Skill Lab

## Purpose

Create and maintain a Codex-friendly FDE skill package that turns messy customer materials into implementation-ready artifacts.

The project focuses on upstream FDE reasoning, benchmark evaluation, and safe handoff to downstream coding agents.

## Primary User

- FDE / applied AI delivery lead
- VitaClaw implementation architect
- Codex or another coding agent working from FDE artifacts

## Core Problem

Customers rarely provide clean requirements. They provide scattered documents, field checklists, interviews, examples, screenshots, and business pain.

This repo defines how an agent should convert that mess into:

- one bounded operator loop
- business object and evidence model
- source-of-truth and validation matrix
- PRD
- UAT plan
- coding-agent handoff contract

## Non-Goals

- Building the actual application
- OCR/PDF parsing implementation
- Web UI implementation
- OpenClaw runtime integration
- Meeting copilot / ASR / TTS
- Production browser automation

## Success Criteria

The skill passes when it can reconstruct a benchmark project from messy inputs and produce artifacts close enough for a coding agent to implement safely.

The first benchmark is Export Label Helper.
