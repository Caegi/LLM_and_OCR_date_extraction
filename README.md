# Our problematics:

Through carefuly analysis of the baseline solution and our own experimentations, we've been targetting at tackling:

-Date missing in the extracted text due to inadequate OCR or leaving out pages(e.g. date information in irregular font or image format, and dates appearing at the end of the document)

-Lack of a benchmark dataset and a set of consistent annotation rules with high-quality human annotation on which to test and improve the predictor.

-Economize the computation of LLM's inference by giving as the input only most relevant informations

-Fully utilize the LLM's knowledge to make a good judgement among several possible dates and even correct some OCR errors

Responding to the above problematics, we present:

# Highlights of the work:

    Better quality OCR(we used the best-performing open-source OCR model we found: PaddleOCR by Baidu China), especially effective for keeping and recognizing the dates of irregular font/format

    A benchmark dataset strictly annotated by our native French members following a set of reasonable and consistent annotation rules(see evaluation part), including the most challenging examples

    Economize the computation of LLM while keeping good performance with a highly efficient input: NER Dates with their contexutal characters of the doc's first pages and final pages

    Utilize the prompting(few-shot learning and simple CoT) to refine LLM(Qwen)'s inference and further compensente inevitable OCR flaws

# Result
Compared with the Datapolitcs baseline, our predictor shows obvious performance improvement(more than 10% on our challenge benchmark dataset and more than 5% on the class's collaborative annotation dataset, see the Evaluation part)

# Pipeline:

    PDF and original Data preparation

    OCR: PDF(to image)to Text

    NER dates extraction with contextual information

    LLM(Qwen 2.5)-based predictor(prompted)

    Evaluation

