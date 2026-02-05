# cortex-ai
project for aws
# Agro-Guard Saathi - Requirements Document

## Project Overview

Agro-Guard Saathi is a proactive AI-driven agricultural crisis management system designed for rural Indian farmers. The system addresses the ₹2.5 Lakh Crore annual crop loss crisis by providing 4-hour early warnings and instant crop disease diagnosis through AWS Bedrock-powered vernacular communication.

## Target Audience

**Primary Users**: Rural Indian farmers with limited literacy and low-bandwidth internet access
- Basic feature phone users with WhatsApp capability
- Hindi and Marathi speaking farmers
- Small and marginal farmers (like "Ramesh from Nashik")
- Users in areas with poor internet connectivity ("dark zones")

## Functional Requirements (EARS Notation)

### FR-1: Crop Disease Image Analysis

**WHEN** a farmer uploads a crop image via WhatsApp, **THE** system **SHALL** analyze the image using Amazon Bedrock (Claude 3.5 Sonnet) within 60 seconds.

**WHEN** the image analysis is complete, **THE** system **SHALL** identify diseases, pests, and nutrient deficiencies with confidence scores.

**WHERE** image quality is insufficient for analysis, **THE** system **SHALL** request a clearer image with specific guidance in Hindi or Marathi.

### FR-2: Multilingual Support

**THE** system **SHALL** support Hindi as the primary language and Marathi as the secondary language for all farmer communications.

**WHEN** providing diagnosis results, **THE** system **SHALL** generate responses in the farmer's preferred language (Hindi or Marathi).

**THE** system **SHALL** use Amazon Polly for text-to-speech conversion with appropriate regional voices:
- Hindi: Aditi (female) voice
- Marathi: Hindi voice with Marathi text processing

### FR-3: Severity-Based Alert Routing

**WHEN** disease severity is assessed, **THE** system **SHALL** classify threats on a scale of 1-10.

**IF** severity score is greater than 7, **THEN** **THE** system **SHALL** trigger an automated voice call using Amazon Connect within 2 minutes.

**IF** severity score is 7 or below, **THEN** **THE** system **SHALL** send treatment advice via WhatsApp text message.

**WHEN** making voice calls, **THE** system **SHALL** use Amazon Polly to generate vernacular speech in the farmer's preferred language.

### FR-4: Low-Bandwidth Optimization

**THE** system **SHALL** compress uploaded images to less than 500KB while maintaining diagnostic quality.

**WHERE** WhatsApp delivery fails due to connectivity issues, **THE** system **SHALL** fall back to SMS for critical alerts.

**THE** system **SHALL** support offline message queuing for farmers in areas with intermittent connectivity.

### FR-5: Farmer Profile Management

**THE** system **SHALL** store farmer profiles in DynamoDB including:
- Location coordinates (latitude, longitude)
- Language preference (Hindi/Marathi)
- Communication preference (voice/text/both)
- Crop types and farm size
- Contact information (phone, WhatsApp)

**WHEN** a farmer interacts with the system for the first time, **THE** system **SHALL** create a profile with default settings.

### FR-6: Proactive Weather Alerts

**WHEN** satellite data indicates weather threats within 4 hours of a farmer's location, **THE** system **SHALL** trigger immediate alerts.

**IF** the threat is classified as life-threatening, **THEN** **THE** system **SHALL** initiate automated voice calls in Hindi or Marathi.

**THE** system **SHALL** provide actionable advice such as "Harvest now—rain in 4 hours" in the farmer's vernacular language.

## Non-Functional Requirements

### NFR-1: Performance
- **Response Time**: Image analysis completed within 60 seconds
- **Voice Call Initiation**: Critical alerts triggered within 2 minutes
- **System Availability**: 99.9% uptime during agricultural seasons

### NFR-2: Scalability
- **Concurrent Users**: Support for millions of farmers simultaneously
- **Serverless Architecture**: AWS Lambda for automatic scaling
- **Cost Optimization**: Zero cost when system is idle

### NFR-3: Accessibility
- **Language Support**: Hindi and Marathi with expansion capability
- **Device Compatibility**: Works on basic feature phones with WhatsApp
- **Connectivity**: Optimized for low-bandwidth rural internet connections

### NFR-4: Security
- **Data Encryption**: All farmer data encrypted at rest and in transit
- **Privacy**: Automatic deletion of crop images after 30 days
- **Access Control**: Role-based access for system administrators

## Acceptance Criteria

### AC-1: Image Analysis Workflow
- ✅ Farmer uploads crop image via WhatsApp
- ✅ System processes image using Amazon Bedrock within 60 seconds
- ✅ Disease identification with confidence scores provided
- ✅ Treatment recommendations generated in Hindi/Marathi

### AC-2: Severity-Based Routing
- ✅ Severity > 7: Automated voice call triggered within 2 minutes
- ✅ Severity ≤ 7: WhatsApp text response sent
- ✅ Voice calls delivered in farmer's preferred language
- ✅ SMS fallback for connectivity issues

### AC-3: Multilingual Communication
- ✅ Hindi support with Aditi voice
- ✅ Marathi support with appropriate text processing
- ✅ Farmer language preference stored and respected
- ✅ All responses culturally appropriate and locally relevant

### AC-4: Low-Bandwidth Support
- ✅ Image compression to <500KB
- ✅ SMS fallback for critical alerts
- ✅ Offline message queuing capability
- ✅ Progressive loading for slow connections

## Constraints

### Technical Constraints
- Must use AWS Bedrock (Claude 3.5 Sonnet) for all AI operations
- Serverless architecture required (AWS Lambda, DynamoDB, S3)
- Hindi and Marathi language priority over other regional languages
- Integration with WhatsApp Business API mandatory

### Business Constraints
- Target audience: Rural Indian farmers with basic phones
- Focus on Maharashtra and Hindi-speaking regions initially
- Cost-effective solution for small and marginal farmers
- Compliance with Indian data localization requirements

## Glossary

- **EARS**: Easy Approach to Requirements Syntax
- **Golden Window**: 4-hour early warning period for disaster prevention
- **Severity Score**: 1-10 scale for disease/threat classification
- **Vernacular Communication**: Local language (Hindi/Marathi) interaction
- **Dark Zones**: Areas with poor internet connectivity
- **Next Billion Users**: Rural users with basic phones and limited digital literacy
