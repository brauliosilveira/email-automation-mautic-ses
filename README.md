# Email Automation with Mautic and Amazon SES

A marketing automation and lifecycle communication system built around Mautic, Amazon SES, WordPress forms, behavioral tracking, dynamic segmentation, lead scoring, and cross-channel follow-up through WhatsApp.

This repository is presented as a public portfolio case study for recruiters, hiring managers, and founders evaluating senior full-stack product work. It highlights the automation architecture, lead-management strategy, segmentation logic, and multi-channel execution behind the system while keeping the full source code private for commercial and security reasons.

## Executive Summary

This project was built to automate a critical part of the digital sales funnel: turning anonymous website visitors into identified leads with tracked behavior, dynamic segmentation, lifecycle automation, and cross-channel follow-up.

The system combined:

- WordPress as the acquisition layer;
- embedded Mautic forms for lead capture;
- Mautic campaign automation for lifecycle flows;
- Amazon SES for email delivery;
- Mautic tracking for visitor-history mapping;
- dynamic segment-based automation;
- lead scoring based on behavior and conversion events;
- n8n and Evolution API for WhatsApp follow-up after form submission.

The result was a marketing automation stack capable of handling list growth, nurture, attribution, suppression cleanup, segmentation, and sales-oriented follow-up in one operational flow.

## The Problem

Most email automation setups stop at simple form capture and basic email sequences.

That is usually not enough for real commercial operations, because teams also need:

- UTM attribution for acquisition analysis;
- visitor tracking before and after conversion;
- suppression/opt-out handling;
- dynamic segmentation;
- behavior-based lead scoring;
- campaign automation that changes as the lead evolves;
- multi-channel follow-up beyond email.

This project was built to turn a standard signup flow into a more complete lifecycle and revenue automation system.

## What I Built

- WordPress-to-Mautic lead capture integration
- Embedded Mautic forms on the public website
- Automatic contact creation in Mautic after signup
- UTM capture and attribution persistence
- Mautic campaign automation for lifecycle workflows
- Suppression cleanup logic for opt-out recovery when appropriate
- Dynamic lead scoring based on behavior and conversion events
- Tag and segment updates driven by user actions
- Website visitor tracking through Mautic tracking scripts
- Full pre-signup and post-signup behavior visibility when the visitor converted
- n8n-based WhatsApp automation triggered after form submission
- Evolution API integration for WhatsApp messaging
- Segment-driven automation for ebooks, courses, and waitlists

## Use Cases

This automation was used in real commercial scenarios such as:

- ebook sales;
- course sales;
- online course waitlists;
- lead nurturing based on signup source and behavior;
- segment-driven sales and follow-up campaigns.

## Funnel Logic

At a high level, the system worked like this:

### 1. Visitor tracking begins before signup

Mautic tracking was installed on the website to capture anonymous visitor behavior before conversion.

That means once a person eventually filled out a form, the system could connect their known contact record with their previous browsing history.

### 2. Form submission creates or updates the contact

A Mautic form embedded on the WordPress site captured the lead and sent the record into the automation system.

At that moment, the workflow could:

- create or update the contact;
- store UTM tags;
- associate previous visitor tracking history;
- trigger the correct campaign automation.

### 3. Contact state is normalized

After capture, the automation could:

- remove the lead from a `do not contact` state when the context justified reactivation;
- update tags;
- move the lead into the right segment;
- start campaign sequences immediately.

### 4. Scoring evolves with behavior

The system generated score based on actions such as:

- form signup;
- email opens;
- purchase events;
- and other engagement signals.

This made the automation more useful for identifying lead temperature and prioritization.

### 5. Cross-channel follow-up

Email was the core lifecycle channel, but WhatsApp was also triggered through n8n and Evolution API after form submission.

That allowed the system to combine:

- email nurture;
- WhatsApp follow-up;
- segmentation-driven campaign branching.

## Key Capabilities

### UTM attribution capture

The system stored UTM markings so leads could be tied back to traffic source, campaign context, and acquisition origin.

This is especially important for paid traffic and campaign analysis.

### Opt-out aware lifecycle handling

The automation handled contacts that might already be in a `do not contact` state and could remove them from that state when the new signup context indicated valid re-entry into communication flows.

### Dynamic lead scoring

Score was not static. It evolved with engagement and conversion behavior, which made the system more useful for qualification and segmentation.

### Dynamic segments and tags

Tags and segments were updated based on actual user actions, not only on the first form submission.

That made it possible to run more adaptive automation rather than relying on rigid static lists.

### Visitor history continuity

One of the strongest parts of the setup was the ability to preserve and connect visitor history once the anonymous visitor became an identified lead.

This created a much richer lead profile than a form-only setup.

### WhatsApp as a follow-up channel

Using n8n and Evolution API, the system extended lifecycle automation beyond email and into WhatsApp follow-up triggered by form activity.

That made the automation more responsive and more commercially useful.

## Technical Architecture

The system operated across five layers:

### 1. Website acquisition layer

- WordPress
- embedded Mautic forms
- tracked visitor entry points and campaign context

### 2. Contact and campaign automation layer

- Mautic
- forms
- campaigns
- segments
- tags
- scoring
- tracking

### 3. Email delivery layer

- Amazon SES

This provided the delivery infrastructure for lifecycle and campaign emails.

### 4. Workflow orchestration layer

- n8n

Used to trigger WhatsApp actions after form submission and connect marketing events to external messaging flows.

### 5. WhatsApp communication layer

- Evolution API

Used to deliver cross-channel follow-up outside the email channel.

## Technical Flow

### 1. Visitor lands on the website

The visitor browses the WordPress site while being tracked through Mautic tracking.

### 2. Visitor fills out a Mautic form

The lead submits a form for a product, waitlist, ebook, or other campaign entry point.

### 3. Contact record is created or updated

The automation sends the lead into Mautic, preserving attribution and linking the known contact with prior visitor-history data.

### 4. Campaign logic runs

The workflow updates suppression state when appropriate, assigns score, applies tags, and moves the lead into the correct segment.

### 5. Lifecycle communication starts

Email automation starts through Mautic and Amazon SES, while WhatsApp follow-up can also be triggered through n8n and Evolution API.

### 6. Segmentation evolves over time

As the lead engages, opens emails, or purchases, score and segment state can change dynamically, allowing future automation to branch more intelligently.

## Key Engineering Decisions

### Use Mautic as the lifecycle brain, not just as a newsletter tool

The system treated Mautic as a real marketing automation engine, using forms, tracking, scoring, tags, campaigns, and segments together rather than relying on basic static email blasts.

### Preserve visitor history beyond the moment of conversion

Connecting anonymous browsing behavior to the identified lead after signup created stronger lead context and better downstream automation.

### Keep segmentation dynamic

Dynamic tags and segments make automation more adaptive and operationally useful than fixed list membership.

### Use email and WhatsApp together

Email handled lifecycle nurture, while WhatsApp provided faster and more direct follow-up. This made the system more commercially effective than a single-channel automation flow.

### Build attribution into the contact lifecycle

UTM capture was treated as a first-class concern rather than an afterthought, which made the setup more useful for acquisition analysis and campaign reporting.

## Why This Project Matters

This project demonstrates:

- lifecycle marketing automation design;
- campaign and scoring logic beyond simple email sequences;
- attribution-aware lead capture;
- dynamic segmentation and contact-state management;
- multi-channel automation using email and WhatsApp together;
- practical integration between WordPress, Mautic, SES, n8n, and Evolution API;
- product-minded thinking about acquisition, nurture, and conversion.

It also shows a practical business skill: turning form fills into structured, tracked, segmented, and revenue-relevant customer journeys.

## Stack

- WordPress
- Mautic
- Amazon SES
- n8n
- Evolution API
- visitor tracking
- UTM attribution capture
- dynamic segmentation and lead scoring

## High-Level Architecture

```text
Website Visitors
        |
        v
 WordPress + Mautic Forms
        |
        +--> UTM capture
        +--> Mautic visitor tracking
        |
        v
     Mautic Contact Record
        |
        +--> campaigns
        +--> segments
        +--> tags
        +--> scoring
        +--> suppression state updates
        |
        +--> Amazon SES email delivery
        |
        +--> n8n workflow triggers
                 |
                 v
          Evolution API / WhatsApp
```

## Demo and Media

This case study is best supported by screenshots showing lead capture, tracking continuity, segmentation, and campaign flow.

- `Lead Capture - Embedded Mautic Form on WordPress`
- `Contact Timeline - Visitor History and Form Conversion`
- `Campaign Automation - Lifecycle Flow in Mautic`
- `Lead Scoring - Behavior-Based Qualification`
- `Segmentation - Dynamic Tags and Segments`
- `Cross-Channel Follow-Up - Email and WhatsApp Automation`

## About This Repository

This is a public portfolio case study for full-stack, lifecycle marketing, automation, CRM-adjacent systems, and SaaS-focused roles.

The complete source code, internal integrations, secrets, and infrastructure details remain private for commercial and security reasons.

## My Role

I designed and implemented the automation architecture behind the project, including:

- lead-capture integration between WordPress and Mautic;
- lifecycle campaign logic;
- attribution and tracking strategy;
- dynamic segmentation and scoring logic;
- Amazon SES email delivery setup;
- n8n workflow orchestration;
- WhatsApp follow-up integration through Evolution API.

## Contact

If you would like a live walkthrough or want to discuss lifecycle automation, lead scoring systems, email infrastructure, or full-stack roles, feel free to reach out.

- Website: https://www.brauliosilveira.com
- LinkedIn: https://linkedin.com/in/brauliosilveira
- Email: contact@brauliosilveira.com
- YouTube: https://youtube.com/@venderpelowhats
