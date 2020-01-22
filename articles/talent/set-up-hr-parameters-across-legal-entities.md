---
title: Konfigurowanie parametrów modułu Zasoby ludzkie w wielu firmach
description: Należy skonfigurować wspólne parametry dla rekordów współużytkowanych przez wiele firm, takie jak rekordy stanowisk. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 5bd9684b8d5a5847ac212f2ff5214a6bcc3326fd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897057"
---
# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a><span data-ttu-id="893eb-104">Konfigurowanie parametrów modułu Zasoby ludzkie w wielu firmach</span><span class="sxs-lookup"><span data-stu-id="893eb-104">Set up Human resources (HR) parameters across legal entities</span></span>

<span data-ttu-id="893eb-105">Należy skonfigurować wspólne parametry dla rekordów współużytkowanych przez wiele firm, takie jak rekordy stanowisk.</span><span class="sxs-lookup"><span data-stu-id="893eb-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="893eb-106">W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm.</span><span class="sxs-lookup"><span data-stu-id="893eb-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="893eb-107">Niektórych typy rekordów, np. Stanowisko, są współużytkowane w wielu firmach.</span><span class="sxs-lookup"><span data-stu-id="893eb-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="893eb-108">Dla tych rekordów należy skonfigurować wspólne parametry.</span><span class="sxs-lookup"><span data-stu-id="893eb-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="893eb-109">Na przykład na stronie **Udostępniane parametry zasobów ludzkich** można ustawić parametry modułu Zasoby ludzkie dla różnych firm.</span><span class="sxs-lookup"><span data-stu-id="893eb-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="893eb-110">Na stronie **Udostępniane parametry zasobów ludzkich** parametry są pogrupowane według obszarów na podstawie ich funkcji.</span><span class="sxs-lookup"><span data-stu-id="893eb-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="893eb-111">Wcześniej wydane grupy funkcjonalności</span><span class="sxs-lookup"><span data-stu-id="893eb-111">Previously released functionality</span></span>
<span data-ttu-id="893eb-112">Na karcie **Identyfikacja** trzeba wybrać typy identyfikacji, które reprezentują numery identyfikacyjne, które znajdują się na stronie.</span><span class="sxs-lookup"><span data-stu-id="893eb-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="893eb-113">Identyfikację typów należy skonfigurować przed rozpoczęciem wprowadzania informacji identyfikacyjnych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="893eb-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="893eb-114">Informacje o numerze PESEL, numerze dowodu osobistego, numerze obcego dowodu osobistego i osobistym kodzie identyfikacyjnym są obsługiwane na stronie **Typ identyfikacji**.</span><span class="sxs-lookup"><span data-stu-id="893eb-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="893eb-115">Aby zdefiniować nowy typ identyfikacji lub sprawdzić listę istniejących typów, kliknij kolejno opcje **Zarządzanie pracownikami** &gt; **karta Linki** &gt; **Ustawienia** &gt; **Typy identyfikacji**.</span><span class="sxs-lookup"><span data-stu-id="893eb-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="893eb-116">Można wprowadzić prosty kod i opis.</span><span class="sxs-lookup"><span data-stu-id="893eb-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-talent"></a><span data-ttu-id="893eb-117">Jeśli używasz programu Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="893eb-117">If you're using Dynamics 365 Talent</span></span>
<span data-ttu-id="893eb-118">Na karcie **Identyfikacja** trzeba wybrać typy identyfikacji, które reprezentują numery identyfikacyjne, które znajdują się na stronie.</span><span class="sxs-lookup"><span data-stu-id="893eb-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="893eb-119">Identyfikację typów należy skonfigurować przed rozpoczęciem wprowadzania informacji identyfikacyjnych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="893eb-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="893eb-120">Informacje o numerze PESEL, numerze dowodu osobistego, numerze obcego dowodu osobistego i osobistym kodzie identyfikacyjnym są obsługiwane na stronie **Typ identyfikacji**.</span><span class="sxs-lookup"><span data-stu-id="893eb-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="893eb-121">Aby zdefiniować nowy typ identyfikacji lub sprawdzić listę istniejących typów, kliknij kolejno opcje **Zasoby ludzkie** &gt; **Ustawienia** &gt; **Typy identyfikacji**.</span><span class="sxs-lookup"><span data-stu-id="893eb-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="893eb-122">Można wprowadzić prosty kod i opis.</span><span class="sxs-lookup"><span data-stu-id="893eb-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="893eb-123">Na karcie **Sekwencje identyfikatorów** można wybrać kolejne numery używane dla następujących rekordów: numer pracownika, stanowisko, identyfikator zgłoszenia użytkownika, dokumentu I-9, kandydat, dyskusja, identyfikator świadczenia i akcja dotycząca pracowników (jeśli ten typ rekordu jest włączony).</span><span class="sxs-lookup"><span data-stu-id="893eb-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="893eb-124">Do obsługi odwołań do sekwencji identyfikatorów i kodów służy strona listy **Sekwencje identyfikatorów**.</span><span class="sxs-lookup"><span data-stu-id="893eb-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="893eb-125">Aby znaleźć tę stronę, użyj funkcji wyszukiwania stron.</span><span class="sxs-lookup"><span data-stu-id="893eb-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="893eb-126">Na karcie **Stanowiska** określ, czy są dostępne nowe stanowiska do domyślnego przypisania:</span><span class="sxs-lookup"><span data-stu-id="893eb-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="893eb-127">**Zawsze** — Można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk.</span><span class="sxs-lookup"><span data-stu-id="893eb-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="893eb-128">Podczas tworzenia stanowisk data i godzina w obszarze **Dostępne do przypisania** na karcie **Ogólne** na stronie **Stanowisko** są automatycznie ustawiane na datę i godzinę utworzenia.</span><span class="sxs-lookup"><span data-stu-id="893eb-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="893eb-129">**Nigdy** — nie można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk.</span><span class="sxs-lookup"><span data-stu-id="893eb-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="893eb-130">Jeśli zostanie wybrana ta opcja, należy otworzyć stronę **Stanowisko** dla każdego nowego stanowiska, gdy staje się dostępne, a następnie na karcie **Ogólne** wpisać datę **Dostępne do przypisania**, aby umożliwić przypisanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="893eb-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="additional-resources"></a><span data-ttu-id="893eb-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="893eb-131">Additional resources</span></span>
--------

[<span data-ttu-id="893eb-132">Konfigurowanie parametrów modułu Zasoby ludzkie (HR) specyficznych dla firmy</span><span class="sxs-lookup"><span data-stu-id="893eb-132">Set up company-specific Human resources (HR) parameters</span></span>](set-up-company-specific-hr-parameters.md)



