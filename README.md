# AWS Generative AI CDK Constructs

![Stability: Experimental](https://img.shields.io/badge/stability-Experimental-important.svg?style=for-the-badge)

> All classes are under active development and subject to non-backward compatible changes or removal in any
> future version. These are not subject to the [Semantic Versioning](https://semver.org/) model.
> This means that while you may use them, you may need to update your source code when upgrading to a newer version of this package.

---

[![View on Construct Hub](https://constructs.dev/badge?package=generative-ai-cdk-constructs)](https://constructs.dev/packages/@cdklabs/generative-ai-cdk-constructs)

[![PyPI version](https://img.shields.io/pypi/v/cdklabs.generative-ai-cdk-constructs)](https://pypi.org/project/cdklabs.generative-ai-cdk-constructs/)
[![npm version](https://img.shields.io/npm/v/@cdklabs/generative-ai-cdk-constructs)](https://www.npmjs.com/package/@cdklabs/generative-ai-cdk-constructs)

## Table of contents

- [Introduction](#introduction)
- [CDK Versions](#cdk-versions)
- [Contributing](#contributing)
- [Adding new constructs](#design-guidelines-and-development-guide)
- [Getting Started](#getting-started)
- [Catalog](#catalog)
- [Sample Use Cases](#sample-use-cases)
- [Additional Resources](#additional-resources)
- [Operational Metrics Collection](#operational-metrics-collection)
- [Roadmap](#roadmap)
- [Legal Disclaimer](#legal-disclaimer)

# Introduction

The AWS Generative AI Constructs Library is an open-source extension of the [AWS Cloud Development Kit (AWS CDK)](https://docs.aws.amazon.com/cdk/v2/guide/home.html) that provides multi-service, well-architected patterns for quickly defining solutions in code to create predictable and repeatable infrastructure, called [constructs](https://docs.aws.amazon.com/cdk/v2/guide/constructs.html). The goal of AWS Generative AI CDK Constructs is to help developers build generative AI solutions using pattern-based definitions for their architecture.

The patterns defined in AWS Generative AI CDK Constructs are high level, multi-service abstractions of AWS CDK constructs that have default configurations based on well-architected best practices. The library is organized into logical modules using object-oriented techniques to create each architectural pattern model.

# CDK Versions

AWS Generative AI CDK Constructs and the AWS CDK are independent teams and have different release schedules. Each release of AWS Generative AI CDK Constructs is built against a specific version of the AWS CDK. The [CHANGELOG.md](./CHANGELOG.md) file lists the CDK version associated with each AWS Generative AI Constructs release. For instance, AWS Generative AI CDK Constructs v0.0.0 was built against AWS CDK v2.96.2. This means that to use AWS Generative AI CDK Constructs v0.0.0, your application must include AWS CDK v2.96.2 or later. You can continue to use the latest AWS CDK versions and upgrade the your AWS Generative AI CDK Constructs version when new releases become available.

# Contributing

Contributions of all kinds are welcome! Check out our [contributor guide](./CONTRIBUTING.md)

# Design guidelines and Development guide

If you want to add a new construct to the library, check out our [design guidelines](./DESIGN_GUIDELINES.md), then follow the [development guide](./DEVELOPER_GUIDE.md)

# Getting Started

#### For TypeScript:
- Create or use an existing CDK application in TypeScript.
  - `cdk init app --language typescript`
- Run `npm install @cdklabs/generative-ai-cdk-constructs`
- The package should be added to your package.json.
- Import the library: 
  - `import * as genai from '@cdklabs/generative-ai-cdk-constructs';`

#### For Python:
- Create or use an existing CDK application in Python
  - `cdk init app --language python`
- Install the package:
  - `pip install cdklabs.generative-ai-cdk-constructs`
- Import the library:
  - `import cdklabs.generative_ai_cdk_constructs`

Refer to the documentation for additional guidance on a particular construct: [Catalog](#catalog)

# Catalog

The following constructs are available in the library:

| **Construct** |Description| AWS Services used |
|:-------------|:-------------|:-------------|
| [Data ingestion pipeline](./src/patterns/gen-ai/aws-rag-appsync-stepfn-opensearch/) | Ingestion pipeline providing a RAG (retrieval augmented generation) source for storing documents in a knowledge base. | Amazon OpenSearch, AWS Step Functions, Amazon Bedrock, AWS AppSync, AWS Lambda | 
| [Question answering](./src/patterns/gen-ai/aws-qa-appsync-opensearch/) | Question answering with a large language model (Anthropic Claude V2.1) using a RAG (retrieval augmented generation) source and/or long context. | Amazon OpenSearch, AWS Lambda, Amazon Bedrock, AWS AppSync | 
| [Summarization](./src/patterns/gen-ai/aws-summarization-appsync-stepfn/) | Document summarization with a large language model (Anthropic Claude V2.1). | AWS Lambda, Amazon Bedrock, AWS AppSync and Amazon Elasticache for Redis.  |
| [Lambda layer](./src/patterns/gen-ai/aws-langchain-common-layer/) | Python Lambda layer providing dependencies and utilities to develop generative AI applications on AWS. | AWS Lambda, Amazon Bedrock, Amazon SageMaker | 
| [SageMaker model deployment (Jumpstart)](./src/patterns/gen-ai/aws-model-deployment-sagemaker/README_jumpstart.md) | Deploy a foundation model from Amazon SageMaker JumpStart to an Amazon SageMaker endpoint. | Amazon SageMaker | 
| [SageMaker model deployment (Hugging Face)](./src/patterns/gen-ai/aws-model-deployment-sagemaker/README_hugging_face.md) | Deploy a foundation model from Hugging Face to an Amazon SageMaker endpoint. | Amazon SageMaker | 
| [SageMaker model deployment (Custom)](./src/patterns/gen-ai/aws-model-deployment-sagemaker/README_custom_sagemaker_endpoint.md) | Deploy a foundation model from an S3 location to an Amazon SageMaker endpoint. | Amazon SageMaker | 
| [Amazon Bedrock](./src/cdk-lib/bedrock/README.md) | CDK L2 Constructs for Amazon Bedrock | Amazon Bedrock, Amazon OpenSearch Serverless, AWS Lambda |
| [Amazon OpenSearch Serverless Vector Collection](./src/cdk-lib/opensearchserverless/README.md) | CDK L2 Constructs to create a vector collection | Amazon OpenSearch Vector Index |
| [Amazon OpenSearch Vector Index](./src/cdk-lib/opensearch-vectorindex/README.md) | CDK L1 Custom Resource to create a vector index | Amazon OpenSearch Serverless, AWS Lambda |

# Sample Use Cases

The official samples repository https://github.com/aws-samples/generative-ai-cdk-constructs-samples includes a collection of functional use case implementations to demonstrate the usage of AWS Generative AI CDK Constructs. These can be used in the same way as architectural patterns, and can be conceptualized as an additional "higher-level" abstraction of those patterns. Those patterns (constructs) are composed together into [stacks](https://docs.aws.amazon.com/cdk/latest/guide/stacks.html), forming a "CDK app".

# Additional Resources

| Resource |Description|
|:-------------|:-------------|
| [AWS re:Invent 2023 - Keynote with Dr. Werner Vogels](https://youtu.be/UTRBVPvzt9w?t=6252) | Dr. Werner Vogels, Amazon.com's VP and CTO, announces the AWS Generative AI CDK Constructs during his AWS re:Invent 2023 keynote. |
| [aws-cdk-stack-builder-tool](https://github.com/aws-samples/aws-cdk-stack-builder-tool) | AWS CDK Builder is a browser-based tool designed to streamline bootstrapping of Infrastructure as Code (IaC) projects using the AWS Cloud Development Kit (CDK). |
| [CDK Live! Building generative AI applications and architectures leveraging AWS CDK Constructs!](https://www.youtube.com/watch?v=NI1F4Xxqyr8) | CDK Live! episode focused on building and deploying generative AI applications and architectures on AWS using the AWS Cloud Development Kit (CDK) and the AWS Generative AI CDK Constructs. |

# Operational Metrics Collection

Provided CDK constructs collect anonymous operational metrics to help AWS improve the quality and features of the constructs. Data collection is subject to the AWS Privacy Policy (https://aws.amazon.com/privacy/). To opt out of this feature, simply disable it by setting the construct property "enableOperationalMetric" to false for each construct used. Defaults to true.

# Roadmap

Roadmap is available through the [GitHub Project](https://github.com/orgs/awslabs/projects/136)

# Legal Disclaimer

You should consider doing your own independent assessment before using the content in this library for production purposes. This may include (amongst other things) testing, securing, and optimizing the CDK constructs and other content, provided in this library, based on your specific quality control practices and standards.

***
&copy; Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
