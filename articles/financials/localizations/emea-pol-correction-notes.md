---
title: Noty korygujące
description: Ten temat zawiera informacje dotyczące not korygujących. Nota korygująca jest dokumentem wymaganym lokalnymi przepisami w Polsce. Służy do poprawiania błędów na fakturze od dostawcy.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 263404
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 918672377445758c44a967cea601158f9e279788
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549046"
---
# <a name="correction-notes"></a><span data-ttu-id="30c98-105">Noty korygujące</span><span class="sxs-lookup"><span data-stu-id="30c98-105">Correction notes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30c98-106">Ten temat zawiera informacje dotyczące not korygujących.</span><span class="sxs-lookup"><span data-stu-id="30c98-106">This topic provides information about correction notes.</span></span> <span data-ttu-id="30c98-107">Nota korygująca jest dokumentem wymaganym lokalnymi przepisami w Polsce.</span><span class="sxs-lookup"><span data-stu-id="30c98-107">A correction note is a document that is required by local regulations in Poland.</span></span> <span data-ttu-id="30c98-108">Służy do poprawiania błędów na fakturze od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="30c98-108">It's used to correct errors on a vendor invoice.</span></span> 

<span data-ttu-id="30c98-109">Jeśli dostawca wystawia firmie dokument sprzedaży, ale błędnie wpisze adres firmy lub numer identyfikacyjny podatku od wartości dodanej (VAT), lokalne przepisy w Polsce wymagają, aby firma wystawiła dostawcy notę korygującą.</span><span class="sxs-lookup"><span data-stu-id="30c98-109">If a vendor issues a sales document to a company, but makes a mistake about the company’s address or value-added tax (VAT) identification number, local regulations in Poland require that the company issue a correction note to the vendor.</span></span> <span data-ttu-id="30c98-110">Nota korygująca zawiera zarówno oryginalny tekst, jak i poprawiony tekst.</span><span class="sxs-lookup"><span data-stu-id="30c98-110">A correction note contains both the original text and the corrected text.</span></span> <span data-ttu-id="30c98-111">Noty korygujące można tworzyć, księgować i drukować z arkusza not korygujących.</span><span class="sxs-lookup"><span data-stu-id="30c98-111">You can create, post, and print a correction note from the Correction notes journal.</span></span> <span data-ttu-id="30c98-112">Następujące pola są dostępne w arkuszu not korygujących.</span><span class="sxs-lookup"><span data-stu-id="30c98-112">The following fields are available on the Correction notes journal.</span></span>

| <span data-ttu-id="30c98-113">Pole</span><span class="sxs-lookup"><span data-stu-id="30c98-113">Field</span></span>           | <span data-ttu-id="30c98-114">opis</span><span class="sxs-lookup"><span data-stu-id="30c98-114">Description</span></span>                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="30c98-115">Pokaż</span><span class="sxs-lookup"><span data-stu-id="30c98-115">Show</span></span>            | <span data-ttu-id="30c98-116">Określ, które dokumenty not korygujących mają być pokazywane, zależnie od ich stan księgowania.</span><span class="sxs-lookup"><span data-stu-id="30c98-116">Select which correction note documents to show, based on their posting status.</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="30c98-117">Faktura akonto</span><span class="sxs-lookup"><span data-stu-id="30c98-117">Invoice account</span></span> | <span data-ttu-id="30c98-118">Wybierz numer konta dostawcy dla poprawionej faktury.</span><span class="sxs-lookup"><span data-stu-id="30c98-118">Select the vendor account number for the corrected invoice.</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="30c98-119">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="30c98-119">Invoice</span></span>         | <span data-ttu-id="30c98-120">Wybierz identyfikator faktury wymagającej poprawienia.</span><span class="sxs-lookup"><span data-stu-id="30c98-120">Select the invoice ID for the invoice that must be corrected.</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="30c98-121">Data</span><span class="sxs-lookup"><span data-stu-id="30c98-121">Date</span></span>            | <span data-ttu-id="30c98-122">Dane transakcji na fakturze.</span><span class="sxs-lookup"><span data-stu-id="30c98-122">The invoice transaction date.</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="30c98-123">Nota korygująca</span><span class="sxs-lookup"><span data-stu-id="30c98-123">Correction note</span></span> | <span data-ttu-id="30c98-124">Wprowadź unikatowy numer identyfikacyjny poprawionej faktury.</span><span class="sxs-lookup"><span data-stu-id="30c98-124">Enter a unique identification number for the correction note.</span></span> <span data-ttu-id="30c98-125">Jeśli skonfigurowano kod numeracji dla odwołań do not korygujących, numer noty korygującej zostanie wygenerowany automatycznie.</span><span class="sxs-lookup"><span data-stu-id="30c98-125">If a number sequence code is set up for references to correction notes, the correction note number is automatically generated.</span></span> <span data-ttu-id="30c98-126">Numeracje można ustawiać na stronie **Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="30c98-126">Number sequences can be set up on the **Accounts payable parameters** page.</span></span> |
| <span data-ttu-id="30c98-127">Data dokumentu</span><span class="sxs-lookup"><span data-stu-id="30c98-127">Document date</span></span>   | <span data-ttu-id="30c98-128">Wprowadź datę noty korygującej.</span><span class="sxs-lookup"><span data-stu-id="30c98-128">Enter a date for the correction note.</span></span> <span data-ttu-id="30c98-129">Jeśli nie określisz daty dokumentu, jako data księgowania zostanie użyta bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="30c98-129">If you don't specify a document date, the current date is used as the posting date.</span></span>                                                                                                                                                |
| <span data-ttu-id="30c98-130">Zaksięgowany</span><span class="sxs-lookup"><span data-stu-id="30c98-130">Posted</span></span>          | <span data-ttu-id="30c98-131">Zaznaczenie opcji wskazuje, że wybrana nota korygująca została zaksięgowana.</span><span class="sxs-lookup"><span data-stu-id="30c98-131">A selected option indicates that the selected correction note has been posted.</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="30c98-132">Tekst oryginalny</span><span class="sxs-lookup"><span data-stu-id="30c98-132">Original text</span></span>   | <span data-ttu-id="30c98-133">Wprowadź oryginalny tekst z faktury, który musi zostać poprawiony.</span><span class="sxs-lookup"><span data-stu-id="30c98-133">Enter the original text from the invoice that must be corrected.</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="30c98-134">Poprawiony tekst</span><span class="sxs-lookup"><span data-stu-id="30c98-134">Corrected text</span></span>  | <span data-ttu-id="30c98-135">Wprowadź poprawiony tekst faktury.</span><span class="sxs-lookup"><span data-stu-id="30c98-135">Enter the correct text for the invoice.</span></span>                                                                                                                                                                                                                                  |





