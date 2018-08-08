---
title: "Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania faktur za umowy w programie Microsoft Dynamics 365 for Field Service z fakturami niezależnymi w programie Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 55301ba39dd28fbae5b6c21b1da3c3d9cf6afd8a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a><span data-ttu-id="0d729-103">Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0d729-103">Synchronize agreement invoices in Field Service to free text invoices in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0d729-104">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania faktur za umowy w programie Microsoft Dynamics 365 for Field Service z fakturami niezależnymi w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0d729-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Microsoft Dynamics 365 for Field Service to free text invoices in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0d729-105">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="0d729-105">Templates and tasks</span></span>

<span data-ttu-id="0d729-106">Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0d729-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Finance and Operations.</span></span>

<span data-ttu-id="0d729-107">**Nazwa szablonu w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="0d729-107">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="0d729-108">Faktury za umowy (z Field Service do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="0d729-108">Agreement invoices (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="0d729-109">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="0d729-109">**Names of the tasks in the Data integration project:**</span></span>

- <span data-ttu-id="0d729-110">Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="0d729-110">Invoice headers</span></span>
- <span data-ttu-id="0d729-111">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="0d729-111">Invoice lines</span></span>

<span data-ttu-id="0d729-112">Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:</span><span class="sxs-lookup"><span data-stu-id="0d729-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="0d729-113">Produkty (z Sales do Fin and Ops) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="0d729-113">Accounts (Sales to Fin and Ops) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="0d729-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="0d729-114">Entity set</span></span>

| <span data-ttu-id="0d729-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="0d729-115">Field Service</span></span>  | <span data-ttu-id="0d729-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0d729-116">Finance and Operations</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="0d729-117">faktury</span><span class="sxs-lookup"><span data-stu-id="0d729-117">invoices</span></span>       | <span data-ttu-id="0d729-118">Nagłówki faktur niezależnych dla odbiorców (usługa CDS)</span><span class="sxs-lookup"><span data-stu-id="0d729-118">CDS customer free text invoice headers</span></span> |
| <span data-ttu-id="0d729-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="0d729-119">invoicedetails</span></span> | <span data-ttu-id="0d729-120">Wiersze faktur niezależnych dla odbiorców (usługa CDS)</span><span class="sxs-lookup"><span data-stu-id="0d729-120">CDS customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="0d729-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="0d729-121">Entity flow</span></span>

<span data-ttu-id="0d729-122">Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Finance and Operations za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="0d729-122">Invoices that are created from an agreement in Field Service can be synchronized to Finance and Operations via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="0d729-123">Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Finance and Operations, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**.</span><span class="sxs-lookup"><span data-stu-id="0d729-123">Updates to these invoices will be synchronized to the free text invoices in Finance and Operations if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="0d729-124">Po zaksięgowaniu faktur niezależnych w programie Finance and Operations i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.</span><span class="sxs-lookup"><span data-stu-id="0d729-124">After the free text invoices are posted in Finance and Operations, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="0d729-125">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="0d729-125">Field Service CRM solution</span></span>

<span data-ttu-id="0d729-126">Do jednostki **Faktury** dodano pole **Zawiera wiersze ze źródłem umowy**.</span><span class="sxs-lookup"><span data-stu-id="0d729-126">The **Has Lines With Agreement Origin** field has been added to the **Invoice** entity.</span></span> <span data-ttu-id="0d729-127">To pole pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="0d729-127">This field helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="0d729-128">Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.</span><span class="sxs-lookup"><span data-stu-id="0d729-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="0d729-129">Do jednostki **Wiersz faktury** dodano pole **Zawiera źródło umowy**.</span><span class="sxs-lookup"><span data-stu-id="0d729-129">The **Has Agreement Origin** field has been added to the **Invoice Line** entity.</span></span> <span data-ttu-id="0d729-130">To pole pomaga zagwarantować, że są synchronizowane tylko wiersze faktur utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="0d729-130">This field helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="0d729-131">Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.</span><span class="sxs-lookup"><span data-stu-id="0d729-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="0d729-132">Pole **Data faktury** jest wymagane w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0d729-132">**Invoice date** is a mandatory field in Finance and Operations.</span></span> <span data-ttu-id="0d729-133">W związku z tym musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja.</span><span class="sxs-lookup"><span data-stu-id="0d729-133">Therefore, the field must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="0d729-134">Aby spełnić ten wymóg, dodano następującą logikę:</span><span class="sxs-lookup"><span data-stu-id="0d729-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="0d729-135">Jeśli pole **Data faktury** jest puste w jednostce **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.</span><span class="sxs-lookup"><span data-stu-id="0d729-135">If the **Invoice Date** field is blank on the **Invoice** entity (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="0d729-136">Użytkownik może zmienić wartość w polu **Data faktury**.</span><span class="sxs-lookup"><span data-stu-id="0d729-136">The user can change the **Invoice Date** field.</span></span> <span data-ttu-id="0d729-137">Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli pole **Data faktury** jest puste na fakturze.</span><span class="sxs-lookup"><span data-stu-id="0d729-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** field is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="0d729-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="0d729-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="0d729-139">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0d729-139">In Finance and Operations</span></span>

<span data-ttu-id="0d729-140">Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Finance and Operations odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service.</span><span class="sxs-lookup"><span data-stu-id="0d729-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Finance and Operations that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="0d729-141">Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="0d729-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="0d729-142">Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Finance and Operations i Field Service.</span><span class="sxs-lookup"><span data-stu-id="0d729-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Finance and Operations to Field Service.</span></span>

1. <span data-ttu-id="0d729-143">Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="0d729-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="0d729-144">Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.</span><span class="sxs-lookup"><span data-stu-id="0d729-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="0d729-145">W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.</span><span class="sxs-lookup"><span data-stu-id="0d729-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="0d729-146">W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.</span><span class="sxs-lookup"><span data-stu-id="0d729-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="0d729-147">Zaznacz pole wyboru **Przypisanie typu pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="0d729-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="0d729-148">W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.</span><span class="sxs-lookup"><span data-stu-id="0d729-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="0d729-149">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0d729-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="0d729-150">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="0d729-150">In the Data Integration project</span></span>

<span data-ttu-id="0d729-151">Zadanie: **Wiersze faktury**</span><span class="sxs-lookup"><span data-stu-id="0d729-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="0d729-152">Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Finance and Operations została zaktualizowana i jest zgodna z żądaną wartością.</span><span class="sxs-lookup"><span data-stu-id="0d729-152">Make sure that the default value for the Finance and Operations field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="0d729-153">Wartość domyślna w szablonie to **401100**.</span><span class="sxs-lookup"><span data-stu-id="0d729-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0d729-154">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="0d729-154">Template mapping in Data integration</span></span>

<span data-ttu-id="0d729-155">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="0d729-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a><span data-ttu-id="0d729-156">Faktury za umowy (z Field Service do Fin and Ops): Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="0d729-156">Agreement invoices (Field Service to Fin and Ops): Invoice headers</span></span>

<span data-ttu-id="0d729-157">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="0d729-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a><span data-ttu-id="0d729-158">Faktury za umowy (z Field Service do Fin and Ops): Wiersze faktur</span><span class="sxs-lookup"><span data-stu-id="0d729-158">Agreement invoices (Field Service to Fin and Ops): Invoice lines</span></span>

<span data-ttu-id="0d729-159">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="0d729-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>

