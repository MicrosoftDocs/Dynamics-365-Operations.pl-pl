---
title: "Płatności dodatnie — omówienie"
description: "Ten artykuł zawiera informacje o aparacie płatności dodatnich. Umożliwia on generowania elektronicznej listy czeków, które można okazywać bankowi."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: cb5a674472936a52b624c548fd37079d57eb6cb7
ms.openlocfilehash: 70e0249ccf317a5a59afd97899187ee58409de22
ms.contentlocale: pl-pl
ms.lasthandoff: 12/14/2017

---

# <a name="positive-pay-overview"></a><span data-ttu-id="a7e06-103">Płatności dodatnie — omówienie</span><span class="sxs-lookup"><span data-stu-id="a7e06-103">Positive pay overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a7e06-104">Ten artykuł zawiera informacje o aparacie płatności dodatnich. Umożliwia on generowania elektronicznej listy czeków, które można okazywać bankowi.</span><span class="sxs-lookup"><span data-stu-id="a7e06-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="a7e06-105">Płatności dodatnie służą do generowania elektronicznej listy czeków, które można okazywać bankowi.</span><span class="sxs-lookup"><span data-stu-id="a7e06-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="a7e06-106">Pliki płatności dodatnich ułatwiają bankom zapobieganie oszustwom związanym z czekami.</span><span class="sxs-lookup"><span data-stu-id="a7e06-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="a7e06-107">Administrator konfiguruje płatności dodatnie w celu generowania elektronicznej listy czeków za każdym razem, gdy czeki są drukowane.</span><span class="sxs-lookup"><span data-stu-id="a7e06-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="a7e06-108">Następnie gdy czek jest przedstawiany bankowi, bank porównuje go z wcześniej wysłaną listą czeków.</span><span class="sxs-lookup"><span data-stu-id="a7e06-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="a7e06-109">Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek.</span><span class="sxs-lookup"><span data-stu-id="a7e06-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="a7e06-110">Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="a7e06-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="a7e06-111">Płatność dodatnia jest też nazywana SafePay.</span><span class="sxs-lookup"><span data-stu-id="a7e06-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="a7e06-112">Pliki płatności dodatnich mogą zawierać poufne informacje na temat odbiorców płatności i kwot czeków.</span><span class="sxs-lookup"><span data-stu-id="a7e06-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="a7e06-113">W związku z tym musisz podjąć odpowiednie środki bezpieczeństwa od momentu wygenerowania plików aż do ich odbioru przez bank.</span><span class="sxs-lookup"><span data-stu-id="a7e06-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="a7e06-114">Pliki płatności dodatnich są pobierane zgodnie z instrukcjami pobierania odpowiednimi dla przeglądarki internetowej.</span><span class="sxs-lookup"><span data-stu-id="a7e06-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="a7e06-115">Pliki płatności dodatnich tworzy się za pomocą jednostek danych.</span><span class="sxs-lookup"><span data-stu-id="a7e06-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="a7e06-116">Aby można było wygenerować pliku płatności dodatnich, należy skonfigurować formaty przekształceń kodu XML, które dokonują translacji danych do formatu czytelnego dla banku.</span><span class="sxs-lookup"><span data-stu-id="a7e06-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="a7e06-117">Dla każdego konta bankowego, dla którego chcesz wygenerować informacje o płatnościach dodatnich, należy przypisać format płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="a7e06-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="a7e06-118">Po wygenerowaniu płatności można wygenerować plik płatności dodatnich dla pojedynczej firmy i pojedynczego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="a7e06-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="a7e06-119">Alternatywnie można generować pliki płatności dodatnich dla wielu firm i kont bankowych równocześnie.</span><span class="sxs-lookup"><span data-stu-id="a7e06-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="a7e06-120">Po zapłaceniu czeków wymienionych w pliku płatności dodatnich, otrzymasz numer potwierdzenia z banku.</span><span class="sxs-lookup"><span data-stu-id="a7e06-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="a7e06-121">Następnie można potwierdzić plik płatności dodatnich w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a7e06-121">You can then confirm the positive pay file in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="a7e06-122">Jeśli trzeba zmodyfikować plik płatności dodatnich, można go wycofać.</span><span class="sxs-lookup"><span data-stu-id="a7e06-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="a7e06-123">Wtedy dla każdego czeku w pliku płatności dodatnich jest resetowane pole wskazujące, czy czek jest uwzględniony w pliku płatności dodatnich.</span><span class="sxs-lookup"><span data-stu-id="a7e06-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="a7e06-124">Aby uzyskać więcej informacji, zobacz [Konfigurowanie i generowanie plików płatności dodatnich](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="a7e06-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>




