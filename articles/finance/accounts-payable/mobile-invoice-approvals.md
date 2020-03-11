---
title: Zatwierdzanie faktur na urządzeniach przenośnych
description: Ten temat przedstawia praktyczne podejście do projektowania scenariuszy komórkowych na bazie procesu zatwierdzania faktur od dostawców na urządzeniach komórkowych.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 88ba96b1d9d2f722528a4a920eabe4ab64304a7a
ms.sourcegitcommit: 4f668b23f5bfc6d6502858850d2ed59d7a79cfbb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3059435"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="f52a2-103">Zatwierdzanie faktur na urządzeniach przenośnych</span><span class="sxs-lookup"><span data-stu-id="f52a2-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f52a2-104">Opcje mobilne pozwalają użytkownikom biznesowym na projektowanie środowiska mobilnego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="f52a2-105">W scenariuszach zaawansowanych platforma umożliwia również deweloperom rozszerzanie funkcjonalności zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="f52a2-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="f52a2-106">Najbardziej skutecznym sposobem, aby poznać niektóre nowe koncepcje obsługi na telefonach komórkowych, jest przejście przez proces projektowania w kilku scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="f52a2-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="f52a2-107">Ten temat przedstawia praktyczne podejście do projektowania scenariuszy komórkowych na bazie procesu zatwierdzania faktur od dostawców na urządzeniach komórkowych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="f52a2-108">Ten temat powinien ułatwić projektowanie w innych wariantach scenariuszy i może być również wykorzystywany w innych scenariuszach, niezwiązanych z fakturami od dostawców.</span><span class="sxs-lookup"><span data-stu-id="f52a2-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="f52a2-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f52a2-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="f52a2-110">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="f52a2-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="f52a2-111">opis</span><span class="sxs-lookup"><span data-stu-id="f52a2-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f52a2-112">Podręcznik wprowadzający do platformy komórkowej</span><span class="sxs-lookup"><span data-stu-id="f52a2-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="f52a2-113">Platforma mobilna</span><span class="sxs-lookup"><span data-stu-id="f52a2-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="f52a2-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="f52a2-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="f52a2-115">Środowisko, w którym zainstalowano wersję 1611 oraz aktualizację nr 3 platformy (z listopada 2016 r.)</span><span class="sxs-lookup"><span data-stu-id="f52a2-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="f52a2-116">Instalacja poprawki KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="f52a2-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="f52a2-117">Rejestrator zadań może błędnie nagrywać dwa polecenia Zamknij dla rozwijanych okien dialogowych; Poprawka jest dołączona do aktualizacji nr 3 platformy (aktualizacja z listopada 2016 r.).</span><span class="sxs-lookup"><span data-stu-id="f52a2-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="f52a2-118">Instalacja poprawki KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="f52a2-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="f52a2-119">Ta poprawka umożliwia wyświetlanie załączników na klientach mobilnych. Poprawka jest dołączona do aktualizacji nr 3 platformy (aktualizacja z listopada 2016 r.).</span><span class="sxs-lookup"><span data-stu-id="f52a2-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="f52a2-120">Instalacja poprawki KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="f52a2-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="f52a2-121">Kod źródłowy aplikacji zatwierdzania faktur od dostawców na urządzeniach komórkowych; również w wersji 7.0.1 (z maja 2016 r.).</span><span class="sxs-lookup"><span data-stu-id="f52a2-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="f52a2-122">Urządzenie z systemem Android, iOS lub Windows, na którym zainstalowano aplikację.</span><span class="sxs-lookup"><span data-stu-id="f52a2-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="f52a2-123">Wyszukaj aplikację w odpowiednim sklepie z aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="f52a2-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="f52a2-124">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="f52a2-124">Introduction</span></span>
<span data-ttu-id="f52a2-125">Aby można było zatwierdzać faktury od dostawców na urządzeniach komórkowych, należy zainstalować trzy poprawki wymienione w sekcji „Wymagania wstępne”.</span><span class="sxs-lookup"><span data-stu-id="f52a2-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="f52a2-126">Te poprawki nie udostępniają obszaru roboczego dla zatwierdzania faktur.</span><span class="sxs-lookup"><span data-stu-id="f52a2-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="f52a2-127">Aby się dowiedzieć, czym jest obszar roboczy w kontekście pracy na urządzeniach komórkowych, przeczytaj podręcznik o platformie komórkowej wymieniony w sekcji „Wymagania wstępne”.</span><span class="sxs-lookup"><span data-stu-id="f52a2-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="f52a2-128">Obszar roboczy zatwierdzania faktur musi być zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="f52a2-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="f52a2-129">Każda organizacja inaczej przygotowuje i definiuje proces biznesowy faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="f52a2-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="f52a2-130">Przed rozpoczęciem projektowania komórkowego środowiska obsługi zatwierdzenia faktur od dostawców należy rozważyć następujące aspekty procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="f52a2-131">Chcemy, aby korzystać z tych punktów w najszerszym możliwym zakresie w celu zoptymalizowania środowiska użytkownika na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="f52a2-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="f52a2-132">Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="f52a2-133">Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="f52a2-134">Ile wierszy faktury istnieje w fakturze?</span><span class="sxs-lookup"><span data-stu-id="f52a2-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="f52a2-135">Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.</span><span class="sxs-lookup"><span data-stu-id="f52a2-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="f52a2-136">Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym?</span><span class="sxs-lookup"><span data-stu-id="f52a2-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="f52a2-137">Jeśli odpowiedź na to pytanie jest twierdząca, należy rozważyć następujące kwestie:</span><span class="sxs-lookup"><span data-stu-id="f52a2-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="f52a2-138">Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty, podziały itd.) istnieje dla wiersza faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="f52a2-139">Tu również zastosuj regułę 80-20.</span><span class="sxs-lookup"><span data-stu-id="f52a2-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="f52a2-140">Czy faktury mają również zasady podziału księgowań w nagłówku faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="f52a2-141">Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-141">If so, should these accounting distributions be available on the device?</span></span>

    > [!NOTE]
    > <span data-ttu-id="f52a2-142">W tym temacie nie wyjaśniono, jak edytować zasady podziału księgowań, ponieważ ta funkcja aktualnie nie jest obsługiwana w scenariuszach mobilnych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="f52a2-143">Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="f52a2-144">Projekt komórkowego środowiska obsługi zatwierdzania faktur będzie się różnił w zależności od odpowiedzi na te pytania.</span><span class="sxs-lookup"><span data-stu-id="f52a2-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="f52a2-145">Celem jest optymalizacja środowiska obsługi procesu biznesowego na urządzeniach komórkowych w organizacji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="f52a2-146">W pozostałej części tego tematu przyjrzymy się dwóm wariantom scenariusza, które są oparte na różnych odpowiedziach na powyższe pytania.</span><span class="sxs-lookup"><span data-stu-id="f52a2-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="f52a2-147">Jako ogólną wskazówkę należy pamiętać, aby podczas pracy w projektancie środowiska komórkowego „publikować” zmiany w celu uniknięcia utraty aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="f52a2-148">Projektowanie prostego scenariusza zatwierdzania faktur dla firmy Contoso</span><span class="sxs-lookup"><span data-stu-id="f52a2-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f52a2-149">Atrybut scenariusza</span><span class="sxs-lookup"><span data-stu-id="f52a2-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="f52a2-150">Odbierz</span><span class="sxs-lookup"><span data-stu-id="f52a2-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f52a2-151">Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="f52a2-152">Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="f52a2-152">Vendor name</span></span></li>
<li><span data-ttu-id="f52a2-153">Suma faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-153">Invoice total</span></span></li>
<li><span data-ttu-id="f52a2-154">Faktura akonto</span><span class="sxs-lookup"><span data-stu-id="f52a2-154">Invoice account</span></span></li>
<li><span data-ttu-id="f52a2-155">Numer faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-155">Invoice number</span></span></li>
<li><span data-ttu-id="f52a2-156">Data faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-156">Invoice date</span></span></li>
<li><span data-ttu-id="f52a2-157">Opis faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-157">Invoice description</span></span></li>
<li><span data-ttu-id="f52a2-158">Termin</span><span class="sxs-lookup"><span data-stu-id="f52a2-158">Due date</span></span></li>
<li><span data-ttu-id="f52a2-159">Waluta faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-160">Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="f52a2-161">Kategoria zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="f52a2-161">Procurement category</span></span></li>
<li><span data-ttu-id="f52a2-162">Ilość</span><span class="sxs-lookup"><span data-stu-id="f52a2-162">Quantity</span></span></li>
<li><span data-ttu-id="f52a2-163">Cena jednostkowa</span><span class="sxs-lookup"><span data-stu-id="f52a2-163">Unit price</span></span></li>
<li><span data-ttu-id="f52a2-164">Kwota netto wiersza</span><span class="sxs-lookup"><span data-stu-id="f52a2-164">Line net amount</span></span></li>
<li><span data-ttu-id="f52a2-165">Wartość 1099</span><span class="sxs-lookup"><span data-stu-id="f52a2-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-166">Ile wierszy faktury istnieje w fakturze?</span><span class="sxs-lookup"><span data-stu-id="f52a2-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="f52a2-167">Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.</span><span class="sxs-lookup"><span data-stu-id="f52a2-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="f52a2-168">1</span><span class="sxs-lookup"><span data-stu-id="f52a2-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-169">Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym?</span><span class="sxs-lookup"><span data-stu-id="f52a2-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="f52a2-170">Tak</span><span class="sxs-lookup"><span data-stu-id="f52a2-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-171">Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty itd.) istnieje dla wiersza faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="f52a2-172">Tu również zastosuj regułę 80-20.</span><span class="sxs-lookup"><span data-stu-id="f52a2-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="f52a2-173">Cena rozszerzona: 2 Podatek: 0 Opłaty: 0</span><span class="sxs-lookup"><span data-stu-id="f52a2-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-174">Czy faktury mają również zasady podziału księgowań w nagłówku faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="f52a2-175">Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="f52a2-176">Nieużywane</span><span class="sxs-lookup"><span data-stu-id="f52a2-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-177">Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="f52a2-178">Tak</span><span class="sxs-lookup"><span data-stu-id="f52a2-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="f52a2-179">Tworzenie obszaru roboczego</span><span class="sxs-lookup"><span data-stu-id="f52a2-179">Create the workspace</span></span>

1.  <span data-ttu-id="f52a2-180">W przeglądarce i zaloguj się do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="f52a2-181">Po zalogowaniu dołącz wyrażenie **&mode=mobile** do adresu URL, jak pokazano w przykładzie poniżej, i odśwież stronę: https://&lt;TwójadresURL&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="f52a2-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="f52a2-182">Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="f52a2-183">Musi zostać wyświetlony projektant aplikacji komórkowych, tak jak się pojawia Rejestrator zadań.</span><span class="sxs-lookup"><span data-stu-id="f52a2-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="f52a2-184">Kliknij przycisk **Dodaj**, aby utworzyć nowy obszar roboczy.</span><span class="sxs-lookup"><span data-stu-id="f52a2-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="f52a2-185">W tym przykładzie nazwij obszar roboczy **Moje zatwierdzenia**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="f52a2-186">Wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="f52a2-186">Enter a description.</span></span>
6.  <span data-ttu-id="f52a2-187">Wybierz kolor dla obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-187">Select a workspace color.</span></span> <span data-ttu-id="f52a2-188">Kolor obszaru roboczego będzie stosowany do ogólnego stylu komórkowego środowiska obsługi w tym obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="f52a2-189">Wybierz ikonę dla obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="f52a2-190">Kliknij przycisk **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-190">Click **Done**</span></span>
9.  <span data-ttu-id="f52a2-191">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="f52a2-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="f52a2-192">Faktury od dostawcy przypisane do mnie</span><span class="sxs-lookup"><span data-stu-id="f52a2-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="f52a2-193">Pierwszą stroną środowiska mobilnego, jaką należy zaprojektować, jest lista faktur przypisanych użytkownikowi w celu weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="f52a2-194">Aby zaprojektować tę stronę dla urządzeń przenośnych, użyj strony **VendMobileInvoiceAssignedToMeListPage** strony.</span><span class="sxs-lookup"><span data-stu-id="f52a2-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="f52a2-195">Przed wykonaniem tej procedury upewnij się, że co najmniej jedna faktura od dostawcy jest Ci przypisana do weryfikacji, a wiersz tej faktury ma dwie dystrybucje.</span><span class="sxs-lookup"><span data-stu-id="f52a2-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="f52a2-196">Ta konfiguracja spełnia wymagania tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f52a2-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="f52a2-197">W adresie URL zastąp nazwę elementu menu wyrażeniem **VendMobileInvoiceAssignedToMeListPage**, aby otwierać mobilną wersję strony listy **Oczekujące faktury od dostawcy — przypisane do mnie** w module **rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="f52a2-198">W zależności od liczby faktur, które zostały w systemie przypisane do Ciebie, na tej stronie będą wyświetlane te faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="f52a2-199">Aby znaleźć konkretną fakturę, możesz użyć filtru z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="f52a2-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="f52a2-200">Jednak w tym przykładzie nie potrzebujemy konkretnej faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="f52a2-201">Musisz mieć tylko przypisaną jakąś fakturę, co umożliwi Ci projektowanie strony mobilnej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="f52a2-202">Nowe strony, które są dostępne, zostały zaprojektowane specjalnie do tworzenia scenariuszy mobilnych dla faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="f52a2-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="f52a2-203">W związku z tym należy używać tych stron.</span><span class="sxs-lookup"><span data-stu-id="f52a2-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="f52a2-204">Adres URL powinien przypominać poniższy adres URL, a po jego wprowadzeniu musi zostać wyświetlona strona przedstawiona na rysunku: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span><span class="sxs-lookup"><span data-stu-id="f52a2-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span></span> 

    <span data-ttu-id="f52a2-205">[![Strona Oczekujące faktury od dostawcy — przypisane do mnie](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-205">[![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
    
2.  <span data-ttu-id="f52a2-206">Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-206">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="f52a2-207">Zaznacz swój obszar roboczy i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-207">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="f52a2-208">Kliknij przycisk **Dodaj stronę**, aby utworzyć pierwszą stronę dla urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-208">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="f52a2-209">Wprowadź nazwę, taką jak **Moje faktury od dostawców**, oraz opis, taki jak **Faktury od dostawców przypisane mi do weryfikacji**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-209">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="f52a2-210">Kliknij przycisk **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-210">Click **Done**.</span></span>
7.  <span data-ttu-id="f52a2-211">W projektancie środowiska komórkowego na karcie **Pola** kliknij przycisk **Wybierz pola**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-211">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="f52a2-212">Kolumny na stronie listy muszą przypominać te na ilustracji poniżej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-212">The columns on the list page must resemble the following illustration.</span></span> 

    <span data-ttu-id="f52a2-213">[![Kolumny na stronie Oczekujące faktury od dostawcy — przypisane do mnie](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-213">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
    
8.  <span data-ttu-id="f52a2-214">Ze strony listy dodaj wymagane kolumny, które muszą być wyświetlane użytkownikom na stronie dla urządzeń komórkowych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-214">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="f52a2-215">Kolejność dodawania będzie kolejnością, w jakiej pola będą wyświetlane użytkownikowi końcowemu.</span><span class="sxs-lookup"><span data-stu-id="f52a2-215">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="f52a2-216">Jedynym sposobem zmiany kolejności pól będzie ponowne wybranie wszystkich pól.</span><span class="sxs-lookup"><span data-stu-id="f52a2-216">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="f52a2-217">Zgodnie z wymaganiami tego scenariusza wymaganych jest osiem poniższych pól.</span><span class="sxs-lookup"><span data-stu-id="f52a2-217">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="f52a2-218">Jednak niektórzy użytkownicy mogą uznawać, że osiem pól to zbyt wiele informacji na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-218">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="f52a2-219">W związku z tym w widoku listy dla urządzeń przenośnych przedstawimy tylko najważniejsze pola.</span><span class="sxs-lookup"><span data-stu-id="f52a2-219">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="f52a2-220">Pozostałe pola będą wyświetlane w widoku szczegółów, który zaprojektujemy później.</span><span class="sxs-lookup"><span data-stu-id="f52a2-220">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="f52a2-221">Na razie dodamy pola wymienione poniżej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-221">For now, we will add the following fields.</span></span> <span data-ttu-id="f52a2-222">Kliknij znak plusa (**+**) w tych kolumnach, aby dodać je do strony komórkowej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-222">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="f52a2-223">Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="f52a2-223">Vendor name</span></span>
    - <span data-ttu-id="f52a2-224">Suma faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-224">Invoice total</span></span>
    - <span data-ttu-id="f52a2-225">Faktura akonto</span><span class="sxs-lookup"><span data-stu-id="f52a2-225">Invoice account</span></span>
    - <span data-ttu-id="f52a2-226">Numer faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-226">Invoice number</span></span>
    - <span data-ttu-id="f52a2-227">Data faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-227">Invoice date</span></span>

    <span data-ttu-id="f52a2-228">Po dodaniu pól strona środowiska komórkowego musi przypominać ilustrację poniżej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-228">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    
    <span data-ttu-id="f52a2-229">[![Strona po dodaniu pól](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-229">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>

9.  <span data-ttu-id="f52a2-230">Należy także dodać następujące kolumny teraz, aby umożliwić obsługę akcji przepływu pracy później.</span><span class="sxs-lookup"><span data-stu-id="f52a2-230">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="f52a2-231">Pokaż zadanie ukończenia</span><span class="sxs-lookup"><span data-stu-id="f52a2-231">Show complete task</span></span>
    - <span data-ttu-id="f52a2-232">Pokaż zadanie delegowania</span><span class="sxs-lookup"><span data-stu-id="f52a2-232">Show delegate task</span></span>
    - <span data-ttu-id="f52a2-233">Pokaż zadanie wycofania</span><span class="sxs-lookup"><span data-stu-id="f52a2-233">Show recall task</span></span>
    - <span data-ttu-id="f52a2-234">Pokaż zadanie odrzucenia</span><span class="sxs-lookup"><span data-stu-id="f52a2-234">Show reject task</span></span>
    - <span data-ttu-id="f52a2-235">Pokaż zadanie wnioskowania o wykonanie</span><span class="sxs-lookup"><span data-stu-id="f52a2-235">Show request completion task</span></span>
    - <span data-ttu-id="f52a2-236">Pokaż zadanie ponownego przesłania</span><span class="sxs-lookup"><span data-stu-id="f52a2-236">Show resubmit task</span></span>

10. <span data-ttu-id="f52a2-237">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-237">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="f52a2-238">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-238">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="f52a2-239">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-239">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="f52a2-240">W formularzu Parametry modułu rozrachunków z dostawcami w obszarze **Faktura** włącz opcję **Wyświetl sumę faktury na liście oczekujących faktur od dostawców** .</span><span class="sxs-lookup"><span data-stu-id="f52a2-240">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="f52a2-241">Należy zauważyć, że tylko po włączeniu tego parametru będą obliczane sumy faktur z przeznaczeniem do wyświetlenia na stronie listy oczekujących faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="f52a2-241">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="f52a2-242">Jest to nowa funkcja zawarta w poprawce 3208224 stanowiącej wymóg wstępny.</span><span class="sxs-lookup"><span data-stu-id="f52a2-242">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="f52a2-243">Szczegóły faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="f52a2-243">Vendor invoice details</span></span>

<span data-ttu-id="f52a2-244">Aby zaprojektować stronę szczegółów faktur dla urządzeń przenośnych, użyj strony **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-244">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="f52a2-245">Należy zauważyć, że w zależności od liczby faktur istniejących w systemie ta strona pokazuje najstarszą fakturę (tzn. tę, która została utworzona jako pierwsza).</span><span class="sxs-lookup"><span data-stu-id="f52a2-245">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="f52a2-246">Aby znaleźć konkretną fakturę, możesz użyć filtru z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="f52a2-246">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="f52a2-247">Jednak w tym przykładzie nie potrzebujemy konkretnej faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-247">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="f52a2-248">Potrzebujemy po prostu jakichś danych faktury, aby móc zaprojektować stronę dla urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-248">We just require some invoice data so that we can design the mobile page.</span></span> 

<span data-ttu-id="f52a2-249">[![Strona przepływu pracy](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-249">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="f52a2-250">W adresie URL zastąp nazwę elementu menu wyrażeniem **VendMobileInvoiceHeaderDetails**, aby otworzyć formularz.</span><span class="sxs-lookup"><span data-stu-id="f52a2-250">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>

2. <span data-ttu-id="f52a2-251">Otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate).</span><span class="sxs-lookup"><span data-stu-id="f52a2-251">Open the mobile designer from the **Settings** (gear) button.</span></span>

3. <span data-ttu-id="f52a2-252">Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-252">Click the **Edit** button to start edit mode in the workspace.</span></span>

4. <span data-ttu-id="f52a2-253">Zaznacz utworzoną wcześniej stronę **Moje faktury od dostawców** i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-253">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>

5. <span data-ttu-id="f52a2-254">Na karcie **Pola** kliknij nagłówek kolumny **Siatka**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-254">On the **Fields** tab, click the **Grid** column heading.</span></span>

6. <span data-ttu-id="f52a2-255">Kliknij kolejno opcje **Właściwości &gt; Dodaj stronę**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-255">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="f52a2-256">**Uwaga:** Po kliknięciu nagłówka **Siatka** i dodaniu strony automatycznie jest ustanawiana relacja ze stroną szczegółów.</span><span class="sxs-lookup"><span data-stu-id="f52a2-256">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>

7. <span data-ttu-id="f52a2-257">Wprowadź tytuł strony, taki jak **Szczegóły faktury**, oraz opis, taki jak **Wyświetlanie nagłówka i szczegółów wiersza faktury**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-257">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>

8. <span data-ttu-id="f52a2-258">Kliknij przycisk **Wybierz pola**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-258">Click **Select fields**.</span></span> <span data-ttu-id="f52a2-259">Pamiętaj, że kolejność dodawania będzie kolejnością, w jakiej pola będą wyświetlane użytkownikowi końcowemu.</span><span class="sxs-lookup"><span data-stu-id="f52a2-259">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="f52a2-260">Jedynym sposobem zmiany kolejności pól będzie ponowne wybranie wszystkich pól.</span><span class="sxs-lookup"><span data-stu-id="f52a2-260">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 

9. <span data-ttu-id="f52a2-261">Zgodnie z wymaganiami tego scenariusza dodaj następujące pola z nagłówka:</span><span class="sxs-lookup"><span data-stu-id="f52a2-261">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="f52a2-262">Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="f52a2-262">Vendor name</span></span>
   - <span data-ttu-id="f52a2-263">Suma faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-263">Invoice total</span></span>
   - <span data-ttu-id="f52a2-264">Faktura akonto</span><span class="sxs-lookup"><span data-stu-id="f52a2-264">Invoice account</span></span>
   - <span data-ttu-id="f52a2-265">Numer faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-265">Invoice number</span></span>
   - <span data-ttu-id="f52a2-266">Data faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-266">Invoice date</span></span>
   - <span data-ttu-id="f52a2-267">Opis faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-267">Invoice description</span></span>
   - <span data-ttu-id="f52a2-268">Termin</span><span class="sxs-lookup"><span data-stu-id="f52a2-268">Due date</span></span>
   - <span data-ttu-id="f52a2-269">Waluta faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-269">Invoice currency</span></span>

10. <span data-ttu-id="f52a2-270">Dodaj następujące pola z siatki wierszy na stronie:</span><span class="sxs-lookup"><span data-stu-id="f52a2-270">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="f52a2-271">Kategoria zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="f52a2-271">Procurement category</span></span>
    - <span data-ttu-id="f52a2-272">Ilość</span><span class="sxs-lookup"><span data-stu-id="f52a2-272">Quantity</span></span>
    - <span data-ttu-id="f52a2-273">Cena jednostkowa</span><span class="sxs-lookup"><span data-stu-id="f52a2-273">Unit price</span></span>
    - <span data-ttu-id="f52a2-274">Kwota netto wiersza</span><span class="sxs-lookup"><span data-stu-id="f52a2-274">Line net amount</span></span>
    - <span data-ttu-id="f52a2-275">Wartość 1099</span><span class="sxs-lookup"><span data-stu-id="f52a2-275">1099 amount</span></span>

11. <span data-ttu-id="f52a2-276">Po dodaniu wszystkich pól z dwóch poprzednich kroków kliknij przycisk **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-276">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="f52a2-277">Strona musi przypominać tę na ilustracji poniżej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-277">The page must resemble the following illustration.</span></span>
    
    <span data-ttu-id="f52a2-278">[![Strona po dodaniu pól](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-278">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>

12. <span data-ttu-id="f52a2-279">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-279">Click **Done** to exit edit mode.</span></span>

13. <span data-ttu-id="f52a2-280">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-280">Click **Back** and then **Done** to exit the workspace</span></span>

14. <span data-ttu-id="f52a2-281">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-281">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="f52a2-282">Akcje przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f52a2-282">Workflow actions</span></span>

<span data-ttu-id="f52a2-283">Aby dodać akcje przepływu pracy użyj strony **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-283">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="f52a2-284">Aby otworzyć tę stronę, należy zastąpić nazwę elementu menu w adresie URL, tak jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="f52a2-284">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="f52a2-285">Następnie otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate).</span><span class="sxs-lookup"><span data-stu-id="f52a2-285">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="f52a2-286">Wykonaj następujące kroki, aby dodać akcje przepływu pracy na stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="f52a2-286">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="f52a2-287">Musisz mieć przypisane faktury będące w stanie umożliwiającym udostępnienie Ci akcji przepływu pracy, dla których zamierzasz projektować środowisko.</span><span class="sxs-lookup"><span data-stu-id="f52a2-287">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="f52a2-288">Rejestrowanie akcji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f52a2-288">Record workflow actions</span></span>
1.  <span data-ttu-id="f52a2-289">Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-289">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="f52a2-290">Zaznacz utworzoną wcześniej stronę **Szczegóły faktury** i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-290">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="f52a2-291">Na karcie **Akcje** kliknij przycisk **Dodaj akcję**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-291">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="f52a2-292">Wprowadź tytuł akcji, taki jak **Zatwierdź**, oraz opis, taki jak **Zatwierdź fakturę**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-292">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="f52a2-293">Należy zauważyć, że tytuł akcji wprowadzony w tym miejscu staje się nazwą akcji wyświetlaną użytkownikowi w aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-293">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="f52a2-294">Kliknij przycisk **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-294">Click **Done**.</span></span>
6.  <span data-ttu-id="f52a2-295">Kliknij przycisk **Wybierz pola**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-295">Click **Select fields**.</span></span>
7.  <span data-ttu-id="f52a2-296">Przejdź przez proces przepływu pracy na stronie **VendMobileInvoiceHeaderDetails** i wykonaj akcję, która miała zostać nagrana.</span><span class="sxs-lookup"><span data-stu-id="f52a2-296">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="f52a2-297">Pamiętaj, aby wprowadzić komentarz do przepływu pracy podczas tego procesu, tak aby pole komentarza również się znalazło w komórkowym środowisku obsługi.</span><span class="sxs-lookup"><span data-stu-id="f52a2-297">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="f52a2-298">Po wykonaniu akcji przepływu pracy kliknij przycisk **Gotowe**, aby ukończyć zadanie Wybierz pola.</span><span class="sxs-lookup"><span data-stu-id="f52a2-298">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="f52a2-299">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-299">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="f52a2-300">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-300">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="f52a2-301">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-301">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="f52a2-302">Powtórz poprzednie kroki, aby zarejestrować wszystkie wymagane akcje przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f52a2-302">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="f52a2-303">Tworzenie pliku .js</span><span class="sxs-lookup"><span data-stu-id="f52a2-303">Create a .js file</span></span>
1. <span data-ttu-id="f52a2-304">Otwórz aplikację Notatnik lub Microsoft Visual Studio i wklej poniższy kod źródłowy.</span><span class="sxs-lookup"><span data-stu-id="f52a2-304">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="f52a2-305">Zapisz plik w formacie .js.</span><span class="sxs-lookup"><span data-stu-id="f52a2-305">Save the file as a .js file.</span></span> <span data-ttu-id="f52a2-306">Ten kod powoduje wykonanie następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f52a2-306">This code does the following:</span></span>
    - <span data-ttu-id="f52a2-307">Ukrywa dodatkowe kolumny dotyczące przepływu pracy, które wcześniej dodano na stronie listy elementów dla urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-307">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="f52a2-308">Dodaliśmy te kolumny, tak aby aplikacja posiadała te informacje w kontekście i mogła wykonać następny krok.</span><span class="sxs-lookup"><span data-stu-id="f52a2-308">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="f52a2-309">Na podstawie aktywnego kroku przepływu pracy zastosuje logikę powodującą pokazanie tylko tych akcji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-309">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f52a2-310">Nazwy stron i innych formantów w kodzie źródłowym muszą być takie same, jak nazwy w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-310">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  <span data-ttu-id="f52a2-311">Przekaż plik kodu źródłowego do obszaru roboczego, wybierając kartę **Logika**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-311">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="f52a2-312">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-312">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="f52a2-313">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-313">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="f52a2-314">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-314">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="f52a2-315">Załączniki faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="f52a2-315">Vendor invoice attachments</span></span>

1. <span data-ttu-id="f52a2-316">Kliknij przycisk **Ustawienia** (koło zębate) w prawym górnym rogu strony, a następnie kliknij opcję **Aplikacja mobilna**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-316">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>

2. <span data-ttu-id="f52a2-317">Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-317">Click the **Edit** button to start edit mode in the workspace.</span></span>

3. <span data-ttu-id="f52a2-318">Zaznacz utworzoną wcześniej stronę <strong>Szczegóły faktury\*\* i kliknij przycisk \*\*Edytuj</strong>.</span><span class="sxs-lookup"><span data-stu-id="f52a2-318">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>

4. <span data-ttu-id="f52a2-319">Ustaw w opcji **Zarządzanie dokumentami** wartość **Tak**, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-319">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="f52a2-320">**Uwaga:** Jeśli nie ma żadnego wymogu wyświetlania załączników na urządzeniu przenośnym, można pozostawić tę opcję ustawioną na **Nie**, co jest ustawieniem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-320">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   
   ![Zarządzanie dokumentami](./media/docmanagement-216x300.png)

5. <span data-ttu-id="f52a2-322">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-322">Click **Done** to exit edit mode.</span></span>

6. <span data-ttu-id="f52a2-323">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-323">Click **Back** and then **Done** to exit the workspace</span></span>

7. <span data-ttu-id="f52a2-324">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-324">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="f52a2-325">Dystrybucje wierszy faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="f52a2-325">Vendor invoice line distributions</span></span>

<span data-ttu-id="f52a2-326">Wymagania dotyczące tego scenariusza potwierdzają, że będzie tylko dystrybucja na poziomie wierszy, a fakturę zawsze będzie miała tylko jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="f52a2-326">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="f52a2-327">Ponieważ ten scenariusz jest prosty, środowisko użytkownika na urządzeniu przenośnym również musi być na tyle proste, aby w celu wyświetlenia dystrybucji użytkownik nie musiał przechodzić kilka poziomów w głąb.</span><span class="sxs-lookup"><span data-stu-id="f52a2-327">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="f52a2-328">Funkcjonalność faktur od dostawców obejmuje opcję wyświetlania wszystkich dystrybucji z nagłówka faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-328">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="f52a2-329">To zachowanie jest potrzebne w scenariuszu mobilnym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-329">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="f52a2-330">W związku z tym użyjemy strony **VendMobileInvoiceAllDistributionTree** do zaprojektowania tej części scenariusza mobilnego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-330">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="f52a2-331">Znajomość wymagań pomaga nam zdecydować, której konkretnej strony należy użyć i jak dokładnie zoptymalizować komórkowe środowisko obsługi dla użytkownika podczas projektowania scenariusza.</span><span class="sxs-lookup"><span data-stu-id="f52a2-331">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="f52a2-332">W drugim scenariuszu użyjemy innej strony do pokazania dystrybucji, ponieważ wymagania w tym scenariuszu się różnią.</span><span class="sxs-lookup"><span data-stu-id="f52a2-332">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="f52a2-333">W adresie URL zastąp nazwę elementu menu tak jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="f52a2-333">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="f52a2-334">Wyświetlona strona powinna przypominać tę na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-334">The page that appears should resemble the following illustration.</span></span>

    <span data-ttu-id="f52a2-335">[![Strona wszystkich dystrybucji](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="f52a2-335">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>

2.  <span data-ttu-id="f52a2-336">Otwórz projektanta środowiska komórkowego za pomocą przycisku **Ustawienia** (koło zębate).</span><span class="sxs-lookup"><span data-stu-id="f52a2-336">Open the mobile designer from the **Settings** (gear) button.</span></span>

3.  <span data-ttu-id="f52a2-337">Kliknij przycisk **Edytuj**, aby uruchomić tryb edycji w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-337">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="f52a2-338">**Uwaga:** Zobaczysz, że dwie nowe strony zostały utworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f52a2-338">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="f52a2-339">System tworzy te strony, ponieważ w poprzedniej sekcji włączone funkcję zarządzania dokumentami.</span><span class="sxs-lookup"><span data-stu-id="f52a2-339">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="f52a2-340">Można zignorować te nowe strony.</span><span class="sxs-lookup"><span data-stu-id="f52a2-340">You can ignore these new pages.</span></span>

4.  <span data-ttu-id="f52a2-341">Kliknij przycisk **Dodaj stronę**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-341">Click **Add page**.</span></span>

5.  <span data-ttu-id="f52a2-342">Wprowadź tytuł strony, taki jak **Widok księgowania**, oraz opis, taki jak **Widok księgowania faktury**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-342">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>

6.  <span data-ttu-id="f52a2-343">Kliknij przycisk **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-343">Click **Done**.</span></span>

7.  <span data-ttu-id="f52a2-344">Na karcie **Pola** kliknij przycisk **Wybierz pola**, zaznacz poniższe pola na stronie dystrybucji, a następnie kliknij przycisk **Gotowe**:</span><span class="sxs-lookup"><span data-stu-id="f52a2-344">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="f52a2-345">Ilość</span><span class="sxs-lookup"><span data-stu-id="f52a2-345">Amount</span></span>
    2.  <span data-ttu-id="f52a2-346">Waluta</span><span class="sxs-lookup"><span data-stu-id="f52a2-346">Currency</span></span>
    3.  <span data-ttu-id="f52a2-347">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="f52a2-347">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="f52a2-348">Nie wybraliśmy kolumny **Opis** z siatki dystrybucji, ponieważ wymagania tego scenariusza potwierdziły, że cena rozszerzona jest jedną kwotą, dla której będą istniały dystrybucje.</span><span class="sxs-lookup"><span data-stu-id="f52a2-348">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="f52a2-349">W związku z tym użytkownik nie będzie potrzebował dodatkowego pola w celu określenia typu kwoty, dla której jest określana dystrybucja.</span><span class="sxs-lookup"><span data-stu-id="f52a2-349">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="f52a2-350">Jednak w następnym scenariuszu **użyjemy** tych informacji, ponieważ wymagania tego scenariusza określają, że dystrybucje istnieją również dla innych typów kwot (na przykład dla podatku).</span><span class="sxs-lookup"><span data-stu-id="f52a2-350">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>

8.  <span data-ttu-id="f52a2-351">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-351">Click **Done** to exit edit mode.</span></span>

9.  <span data-ttu-id="f52a2-352">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-352">Click **Back** and then **Done** to exit the workspace</span></span>

10. <span data-ttu-id="f52a2-353">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-353">Click **Publish workspace** to save your work</span></span>

#### <a name="adding-navigation-to-view-accounting-page"></a><span data-ttu-id="f52a2-354">Dodawanie nawigacji do strony „Wyświetlanie księgowania”</span><span class="sxs-lookup"><span data-stu-id="f52a2-354">Adding navigation to "View accounting" page</span></span>

<span data-ttu-id="f52a2-355">Strona środowiska komórkowego **Widok księgowania** nie jest obecnie połączona z żadną stroną mobilną, które do tej pory zaprojektowaliśmy.</span><span class="sxs-lookup"><span data-stu-id="f52a2-355">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="f52a2-356">Ponieważ użytkownik powinien być w stanie przejść do strony **Widok księgowania** ze strony **Szczegóły faktury** na urządzeniu przenośnym, musimy zapewnić nawigację ze strony **Szczegóły faktury** do strony **Widok księgowania**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-356">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="f52a2-357">Ustanowimy tę nawigację przy użyciu dodatkowej logiki za pomocą kodu źródłowego JavaScript.</span><span class="sxs-lookup"><span data-stu-id="f52a2-357">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="f52a2-358">Otwórz utworzony wcześniej plik .js i dodaj wiersze wyróżnione w poniższym kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-358">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="f52a2-359">Ten kod wykonuje dwa zadania:</span><span class="sxs-lookup"><span data-stu-id="f52a2-359">This code does two things:</span></span>
    1.  <span data-ttu-id="f52a2-360">Pomaga zagwarantować, że użytkownicy nie mogą przechodzić bezpośrednio z obszaru roboczego do strony **Widok księgowania**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-360">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="f52a2-361">Ustanawia formant nawigacji ze strony **Szczegóły faktury** do strony **Widok księgowania**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-361">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="f52a2-362">Nazwy stron i innych formantów w kodzie źródłowym muszą być takie same, jak nazwy w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="f52a2-362">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  <span data-ttu-id="f52a2-363">Przekaż plik kodu źródłowego do obszaru roboczego, wybierając kartę **Logika** w celu zastąpienia poprzedniego kodu.</span><span class="sxs-lookup"><span data-stu-id="f52a2-363">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="f52a2-364">Kliknij przycisk **Gotowe**, aby wyjść z trybu edycji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-364">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="f52a2-365">Kliknij kolejno przyciski **Wstecz** i **Gotowe**, aby wyjść z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="f52a2-365">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="f52a2-366">Kliknij przycisk **Opublikuj obszar roboczy**, aby zapisać swoją pracę.</span><span class="sxs-lookup"><span data-stu-id="f52a2-366">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="f52a2-367">Weryfikacja</span><span class="sxs-lookup"><span data-stu-id="f52a2-367">Validation</span></span>

<span data-ttu-id="f52a2-368">Na urządzeniu przenośnym otwórz aplikację i połącz się z wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="f52a2-368">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="f52a2-369">Koniecznie zaloguj się w firmie, gdzie faktury od dostawców są Ci przypisane do weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-369">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="f52a2-370">Powinna być możliwość wykonania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f52a2-370">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="f52a2-371">Wyświetlenie obszaru roboczego **Moje zatwierdzenia**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-371">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="f52a2-372">Szczegółowe przejście do obszaru roboczego **Moje zatwierdzenia** i wyświetlenie strony **Moje faktury od dostawców**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-372">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="f52a2-373">Szczegółowe przejście do strony **Moje faktury od dostawców** i wyświetlenie listy faktur, które są Ci przypisane.</span><span class="sxs-lookup"><span data-stu-id="f52a2-373">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="f52a2-374">Szczegółowe przejście do jednej z faktur i wyświetlenie szczegółów nagłówka oraz wierszy faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-374">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="f52a2-375">Na stronie szczegółów wyświetlenie łącza do załączników oraz użycie tego łącza w celu przejścia do listy załączników i wyświetlenia załączników.</span><span class="sxs-lookup"><span data-stu-id="f52a2-375">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="f52a2-376">Na stronie szczegółów wyświetlenie łącza do strony **Widok księgowania** oraz użycie tego łącza w celu przejścia do strony dystrybucji i wyświetlenia dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-376">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="f52a2-377">Na stronie szczegółów u dołu kliknięcie menu **Akcje** i wykonanie akcji przepływu pracy mających zastosowanie do etapu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="f52a2-377">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="f52a2-378">Projektowanie skomplikowanego scenariusza zatwierdzania faktur dla firmy Fabrikam</span><span class="sxs-lookup"><span data-stu-id="f52a2-378">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f52a2-379">Atrybut scenariusza</span><span class="sxs-lookup"><span data-stu-id="f52a2-379">Scenario attribute</span></span></th>
<th><span data-ttu-id="f52a2-380">Odbierz</span><span class="sxs-lookup"><span data-stu-id="f52a2-380">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f52a2-381">Które pola z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-381">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="f52a2-382">Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="f52a2-382">Vendor name</span></span></li>
<li><span data-ttu-id="f52a2-383">Kwota faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-383">Invoice amount</span></span></li>
<li><span data-ttu-id="f52a2-384">Faktura akonto</span><span class="sxs-lookup"><span data-stu-id="f52a2-384">Invoice account</span></span></li>
<li><span data-ttu-id="f52a2-385">Numer faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-385">Invoice number</span></span></li>
<li><span data-ttu-id="f52a2-386">Data faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-386">Invoice date</span></span></li>
<li><span data-ttu-id="f52a2-387">Opis faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-387">Invoice description</span></span></li>
<li><span data-ttu-id="f52a2-388">Termin</span><span class="sxs-lookup"><span data-stu-id="f52a2-388">Due date</span></span></li>
<li><span data-ttu-id="f52a2-389">Waluta faktury</span><span class="sxs-lookup"><span data-stu-id="f52a2-389">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-390">Które wiersze z nagłówka faktury użytkownik będzie chciał widzieć w środowisku mobilnym i w jakiej kolejności?</span><span class="sxs-lookup"><span data-stu-id="f52a2-390">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="f52a2-391">Kategoria zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="f52a2-391">Procurement category</span></span></li>
<li><span data-ttu-id="f52a2-392">Ilość</span><span class="sxs-lookup"><span data-stu-id="f52a2-392">Quantity</span></span></li>
<li><span data-ttu-id="f52a2-393">Cena jednostkowa</span><span class="sxs-lookup"><span data-stu-id="f52a2-393">Unit price</span></span></li>
<li><span data-ttu-id="f52a2-394">Kwota netto wiersza</span><span class="sxs-lookup"><span data-stu-id="f52a2-394">Line net amount</span></span></li>
<li><span data-ttu-id="f52a2-395">Wartość 1099</span><span class="sxs-lookup"><span data-stu-id="f52a2-395">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-396">Ile wierszy faktury istnieje w fakturze?</span><span class="sxs-lookup"><span data-stu-id="f52a2-396">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="f52a2-397">Zastosuj tutaj regułę 80-20 i zoptymalizuj dla 80 procent.</span><span class="sxs-lookup"><span data-stu-id="f52a2-397">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="f52a2-398">5</span><span class="sxs-lookup"><span data-stu-id="f52a2-398">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-399">Czy podczas weryfikowania użytkownicy będą chcieli widzieć zasady podziału księgowań (kodowanie faktur) na urządzeniu przenośnym?</span><span class="sxs-lookup"><span data-stu-id="f52a2-399">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="f52a2-400">Tak</span><span class="sxs-lookup"><span data-stu-id="f52a2-400">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-401">Ile zasad podziału księgowań (cena rozszerzona, podatek, opłaty itd.) istnieje dla wiersza faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-401">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="f52a2-402">Tu również zastosuj regułę 80-20.</span><span class="sxs-lookup"><span data-stu-id="f52a2-402">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="f52a2-403">Cena rozszerzona: 2 Podatek: 2 Opłaty: 2</span><span class="sxs-lookup"><span data-stu-id="f52a2-403">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f52a2-404">Czy faktury mają również zasady podziału księgowań w nagłówku faktury?</span><span class="sxs-lookup"><span data-stu-id="f52a2-404">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="f52a2-405">Jeśli tak, czy te zasady podziału księgowań powinny być dostępne w urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-405">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="f52a2-406">Nieużywane</span><span class="sxs-lookup"><span data-stu-id="f52a2-406">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f52a2-407">Czy użytkownicy będą chcieli widzieć załączniki do faktur na urządzeniu?</span><span class="sxs-lookup"><span data-stu-id="f52a2-407">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="f52a2-408">Tak</span><span class="sxs-lookup"><span data-stu-id="f52a2-408">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="f52a2-409">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="f52a2-409">Next steps</span></span>

<span data-ttu-id="f52a2-410">W scenariuszu 1 można wprowadzić zmiany wymienione poniżej zgodnie z wymaganiami scenariusza 2.</span><span class="sxs-lookup"><span data-stu-id="f52a2-410">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="f52a2-411">Informacje w tej sekcji pomogą usprawnić korzystanie z aplikacji komórkowej.</span><span class="sxs-lookup"><span data-stu-id="f52a2-411">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="f52a2-412">Ponieważ w scenariuszu 2 jest potrzebnych więcej wierszy faktury, wymienione poniżej zmiany w projekcie pomogą zoptymalizować środowisko użytkownika na urządzeniu przenośnym:</span><span class="sxs-lookup"><span data-stu-id="f52a2-412">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="f52a2-413">Zamiast przeglądać wiersze faktury na stronie szczegółów (jak w scenariuszu 1), użytkownicy mogą wybrać opcję wyświetlania wierszy na osobnej stronie dla urządzeń komórkowych.</span><span class="sxs-lookup"><span data-stu-id="f52a2-413">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="f52a2-414">Ponieważ w tym scenariuszu jest potrzebny więcej niż jeden wiersz faktury, jeśli do projektowania strony dystrybucji dla urządzeń przenośnych jest używana strona **VendMobileInvoiceAllDistributionTree** (jak w scenariuszu 1), korelowanie wierszu z dystrybucjami może być mylące dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f52a2-414">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="f52a2-415">W związku z tym do projektowania strony dystrybucji użyj strony **VendMobileInvoiceLineDistributionTree**.</span><span class="sxs-lookup"><span data-stu-id="f52a2-415">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="f52a2-416">W idealnej sytuacji w tym scenariuszu dystrybucje powinny być pokazywane w kontekście wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="f52a2-416">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="f52a2-417">W związku z tym upewnij się, że użytkownik może szczegółowo przejść do wiersza, aby zobaczyć stronę dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="f52a2-417">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="f52a2-418">Użyj funkcji łącza do strony, aby ustanowić drążenie wskroś, tak samo, jak to zrobiono dla stron nagłówka i szczegółów w scenariuszu 1.</span><span class="sxs-lookup"><span data-stu-id="f52a2-418">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="f52a2-419">Ponieważ dystrybucje w scenariuszu 2 wymagają więcej niż jednego typu kwoty (podatek, opłaty i tak dalej), warto, aby były wyświetlane opisy typów kwot.</span><span class="sxs-lookup"><span data-stu-id="f52a2-419">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="f52a2-420">(Pominęliśmy te informacje w scenariuszu 1).</span><span class="sxs-lookup"><span data-stu-id="f52a2-420">(We omitted this information in scenario 1.)</span></span>




