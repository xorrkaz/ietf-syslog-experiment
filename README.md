# Experiment Around VELOCE

I wanted to take a YANG device-centric data model and see what using AI together with a copy
of RFC8407bis could do to generate an Internet Draft with the necessary sections, some
examples, and tree diagrams.

The intent is to make YANG module development faster and encourage more documentation to live
in the YANG module itself (only where it makes sense).  The impetus for this experiment is
[VELOCE](https://datatracker.ietf.org/doc/draft-boucadair-veloce-yang/).

## Generative AI Used

I used [Codex](https://openai.com/codex/) from Open AI with the `gpt-5-codex` model with
Medium reasoning.

## Prompt

This is the prompt I gave the AI:

> In this directory is an ietf-syslog YANG module.  I am running an experiment to see if an IETF internet draft can be auto-generated from a YANG module.  Your job is to do that. You have at your disposal the guidelines for YANG module authors in the draft-ietf-netmod-rfc8407bis.txt file.  Additionally, you have the ability to generate YANG trees using the `pyang -f tree` tool.  Create an IETF internet-draft from this YANG module including all relevant sections based on 8407bis.  Use template text from 8407bis in the appropriate draft sections where template text is specified.  Include examples of instance data from the syslog YANG module in both JSON and XML formats.  Provide separate files for the examples as well as embedding them in the draft.  Be sure to use `pyang --tree-line-length 69` when generating YANG trees and `pyang -f yang --keep-comments --yang-line-length 69` when embedding the YANG module in the draft.  Do not embed the full YANG tree in the main document.  Use an appendix for that.  Only use a shortened, high-level tree in the main part of the draft.

## Disclaimer

Nothing in the example `.json` and `.xml` files or the draft `.txt` file was human-authored.  Codex
wrote all the prose and embedded the YANG module that was extracted from RFC9742.
