---
title: Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 943bf04378a8202d676cbabb282a0a6208a92ef3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210011"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="cbffa-103">Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="cbffa-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cbffa-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cbffa-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="cbffa-105">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="cbffa-105">Templates and tasks</span></span>

<span data-ttu-id="cbffa-106">Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cbffa-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="cbffa-107">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="cbffa-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="cbffa-108">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="cbffa-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="cbffa-109">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="cbffa-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="cbffa-110">Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="cbffa-110">Invoice headers</span></span>
- <span data-ttu-id="cbffa-111">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="cbffa-111">Invoice lines</span></span>

<span data-ttu-id="cbffa-112">Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:</span><span class="sxs-lookup"><span data-stu-id="cbffa-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="cbffa-113">Konta (Sales to Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="cbffa-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="cbffa-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="cbffa-114">Entity set</span></span>

| <span data-ttu-id="cbffa-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="cbffa-115">Field Service</span></span>  | <span data-ttu-id="cbffa-116">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="cbffa-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="cbffa-117">faktury</span><span class="sxs-lookup"><span data-stu-id="cbffa-117">invoices</span></span>       | <span data-ttu-id="cbffa-118">Nagłówki faktur niezależnych dla odbiorców (usługa CDS)</span><span class="sxs-lookup"><span data-stu-id="cbffa-118">CDS customer free text invoice headers</span></span> |
| <span data-ttu-id="cbffa-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="cbffa-119">invoicedetails</span></span> | <span data-ttu-id="cbffa-120">Wiersze faktur niezależnych dla odbiorców (usługa CDS)</span><span class="sxs-lookup"><span data-stu-id="cbffa-120">CDS customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="cbffa-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="cbffa-121">Entity flow</span></span>

<span data-ttu-id="cbffa-122">Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Supply Chain Management za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="cbffa-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Common Data Service Data integration project.</span></span> <span data-ttu-id="cbffa-123">Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Supply Chain Management, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="cbffa-124">Po zaksięgowaniu faktur niezależnych w programie Supply Chain Management i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.</span><span class="sxs-lookup"><span data-stu-id="cbffa-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="cbffa-125">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="cbffa-125">Field Service CRM solution</span></span>

<span data-ttu-id="cbffa-126">Do jednostki **Faktury** dodano pole **Zawiera wiersze ze źródłem umowy**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-126">The **Has Lines With Agreement Origin** field has been added to the **Invoice** entity.</span></span> <span data-ttu-id="cbffa-127">To pole pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="cbffa-127">This field helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="cbffa-128">Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.</span><span class="sxs-lookup"><span data-stu-id="cbffa-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="cbffa-129">Do jednostki **Wiersz faktury** dodano pole **Zawiera źródło umowy**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-129">The **Has Agreement Origin** field has been added to the **Invoice Line** entity.</span></span> <span data-ttu-id="cbffa-130">To pole pomaga zagwarantować, że są synchronizowane tylko wiersze faktur utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="cbffa-130">This field helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="cbffa-131">Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.</span><span class="sxs-lookup"><span data-stu-id="cbffa-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="cbffa-132">Pole **Data faktury** jest wymagane w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cbffa-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="cbffa-133">W związku z tym musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja.</span><span class="sxs-lookup"><span data-stu-id="cbffa-133">Therefore, the field must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="cbffa-134">Aby spełnić ten wymóg, dodano następującą logikę:</span><span class="sxs-lookup"><span data-stu-id="cbffa-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="cbffa-135">Jeśli pole **Data faktury** jest puste w jednostce **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.</span><span class="sxs-lookup"><span data-stu-id="cbffa-135">If the **Invoice Date** field is blank on the **Invoice** entity (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="cbffa-136">Użytkownik może zmienić wartość w polu **Data faktury**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-136">The user can change the **Invoice Date** field.</span></span> <span data-ttu-id="cbffa-137">Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli pole **Data faktury** jest puste na fakturze.</span><span class="sxs-lookup"><span data-stu-id="cbffa-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** field is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="cbffa-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="cbffa-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="cbffa-139">W Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="cbffa-139">In Supply Chain Management</span></span>

<span data-ttu-id="cbffa-140">Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Supply Chain Management odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service.</span><span class="sxs-lookup"><span data-stu-id="cbffa-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="cbffa-141">Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="cbffa-142">Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="cbffa-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="cbffa-143">Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="cbffa-144">Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.</span><span class="sxs-lookup"><span data-stu-id="cbffa-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="cbffa-145">W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="cbffa-146">W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="cbffa-147">Zaznacz pole wyboru **Przypisanie typu pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="cbffa-148">W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="cbffa-149">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="cbffa-150">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="cbffa-150">In the Data Integration project</span></span>

<span data-ttu-id="cbffa-151">Zadanie: **Wiersze faktury**</span><span class="sxs-lookup"><span data-stu-id="cbffa-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="cbffa-152">Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Supply Chain Management została zaktualizowana i jest zgodna z żądaną wartością.</span><span class="sxs-lookup"><span data-stu-id="cbffa-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="cbffa-153">Wartość domyślna w szablonie to **401100**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cbffa-154">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="cbffa-154">Template mapping in Data integration</span></span>

<span data-ttu-id="cbffa-155">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="cbffa-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="cbffa-156">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="cbffa-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="cbffa-157">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="cbffa-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="cbffa-158">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Wiersze faktur</span><span class="sxs-lookup"><span data-stu-id="cbffa-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="cbffa-159">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="cbffa-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>
