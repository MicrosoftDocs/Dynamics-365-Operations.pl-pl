---
title: "Konfigurowanie osób podpisujących drukowane formularze"
description: "Dla firm w Czechach, Estonii, na Węgrzech, Litwie, Łotwie, w Polsce i Rosji można skonfigurować osoby podpisujące oraz tytuły dla odbiorców i dostawców, którzy drukują dokumenty, takie jak faktury i zamówienia gotówkowe."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 263464
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 89a4e44144b8cf90e3aa0cabfffb4ed62ef71e40
ms.contentlocale: pl-pl
ms.lasthandoff: 06/29/2017


---

# <a name="set-up-signers-for-print-forms"></a><span data-ttu-id="8d523-103">Konfigurowanie osób podpisujących drukowane formularze</span><span class="sxs-lookup"><span data-stu-id="8d523-103">Set up signers for print forms</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8d523-104">Dla firm w Czechach, Estonii, na Węgrzech, Litwie, Łotwie, w Polsce i Rosji można skonfigurować osoby podpisujące oraz tytuły dla odbiorców i dostawców, którzy drukują dokumenty, takie jak faktury i zamówienia gotówkowe.</span><span class="sxs-lookup"><span data-stu-id="8d523-104">For legal entities in Czech Republic, Estonia, Hungary, Lithuania, Latvia, Poland, and Russia, you can set up signers and titles for customers and vendors that print documents such as invoices and cash orders.</span></span>

<a name="set-up-default-values"></a><span data-ttu-id="8d523-105">Konfigurowanie wartości domyślnych</span><span class="sxs-lookup"><span data-stu-id="8d523-105">Set up default values</span></span>
---------------------

<span data-ttu-id="8d523-106">Aby skonfigurować osoby podpisujące dokumenty drukowane przez firmę, należy użyć strony **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="8d523-106">To set up signers for the documents that a company prints, use the **Officials** page.</span></span> <span data-ttu-id="8d523-107">Można skonfigurować osoby podpisujące i ich tytuły zarówno dla firmy, jak i dla odbiorców lub dostawców, w zależności od typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="8d523-107">You can set up signers and their titles both for the company and for customers or vendors, depending on the document type.</span></span> <span data-ttu-id="8d523-108">W poniższej tabeli opisano karty znajdujące się na stronie **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="8d523-108">The following table describes the tabs on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d523-109">Karta</span><span class="sxs-lookup"><span data-stu-id="8d523-109">Tab</span></span></th>
<th><span data-ttu-id="8d523-110">opis</span><span class="sxs-lookup"><span data-stu-id="8d523-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8d523-111">Ogólne</span><span class="sxs-lookup"><span data-stu-id="8d523-111">General</span></span></td>
<td><span data-ttu-id="8d523-112">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących (dyrektor i główny księgowy), które mogą podpisywać drukowane dokumenty wszystkich typów.</span><span class="sxs-lookup"><span data-stu-id="8d523-112">Add positions and related information for signers (Director and Chief accountant) who can sign print documents of all types.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-113">Księga</span><span class="sxs-lookup"><span data-stu-id="8d523-113">Ledger</span></span></td>
<td><span data-ttu-id="8d523-114">Dodawanie stanowiska i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące wewnętrzne dokumenty finansowe związane z przepływem środków pieniężnych:</span><span class="sxs-lookup"><span data-stu-id="8d523-114">Add the position and related information for signers who can sign the following internal financial documents that are related to cash flow:</span></span>
<ul>
<li><span data-ttu-id="8d523-115">Dokumenty kasowe</span><span class="sxs-lookup"><span data-stu-id="8d523-115">Cash slips</span></span></li>
<li><span data-ttu-id="8d523-116">Raport zaliczek</span><span class="sxs-lookup"><span data-stu-id="8d523-116">Advance report</span></span></li>
<li><span data-ttu-id="8d523-117">Strona księgi kasowej</span><span class="sxs-lookup"><span data-stu-id="8d523-117">Page of cash book</span></span></li>
<li><span data-ttu-id="8d523-118">Wyciąg kasowy zliczania</span><span class="sxs-lookup"><span data-stu-id="8d523-118">Count statement</span></span></li>
<li><span data-ttu-id="8d523-119">Odroczenia*</span><span class="sxs-lookup"><span data-stu-id="8d523-119">Deferrals*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d523-120">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8d523-120">Sales orders</span></span></td>
<td><span data-ttu-id="8d523-121">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty wychodzące związane z odbiorcami:</span><span class="sxs-lookup"><span data-stu-id="8d523-121">Add positions and related information for signers who can sign the following outgoing primary documents that are related to customers:</span></span>
<ul>
<li><span data-ttu-id="8d523-122">Faktura do zapłaty*</span><span class="sxs-lookup"><span data-stu-id="8d523-122">Invoice for payment*</span></span></li>
<li><span data-ttu-id="8d523-123">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="8d523-123">Invoice</span></span></li>
<li><span data-ttu-id="8d523-124">Dokument faktury*</span><span class="sxs-lookup"><span data-stu-id="8d523-124">Facture*</span></span></li>
<li><span data-ttu-id="8d523-125">Faktura — faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="8d523-125">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="8d523-126">Dokument faktury — faktura korygująca*</span><span class="sxs-lookup"><span data-stu-id="8d523-126">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="8d523-127">Dokument faktury transakcji podatku (klient)*</span><span class="sxs-lookup"><span data-stu-id="8d523-127">Tax transaction facture (client)*</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-128">Zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="8d523-128">Purchase orders</span></span></td>
<td><span data-ttu-id="8d523-129">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty przychodzące związane z dostawcami:</span><span class="sxs-lookup"><span data-stu-id="8d523-129">Add positions and related information for signers who can sign the following incoming primary documents that are related to vendors:</span></span>
<ul>
<li><span data-ttu-id="8d523-130">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="8d523-130">Invoice</span></span></li>
<li><span data-ttu-id="8d523-131">Dokument faktury*</span><span class="sxs-lookup"><span data-stu-id="8d523-131">Facture*</span></span></li>
<li><span data-ttu-id="8d523-132">Faktura — faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="8d523-132">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="8d523-133">Dokument faktury — faktura korygująca*</span><span class="sxs-lookup"><span data-stu-id="8d523-133">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="8d523-134">Faktura do zapłaty*</span><span class="sxs-lookup"><span data-stu-id="8d523-134">Invoice for payment*</span></span></li>
<li><span data-ttu-id="8d523-135">Dokument faktury transakcji podatku (dostawca)*</span><span class="sxs-lookup"><span data-stu-id="8d523-135">Tax transaction facture (vendor)*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d523-136">Zarządzanie pozycjami magazynowymi</span><span class="sxs-lookup"><span data-stu-id="8d523-136">Inventory item management</span></span></td>
<td><span data-ttu-id="8d523-137">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące dokumenty magazynowe, gdy materialne środki trwałe są wydawane do odbiorcy lub przyjmowane od dostawcy:</span><span class="sxs-lookup"><span data-stu-id="8d523-137">Add positions and related information for signers who can sign the following warehouse documents when tangible assets are issued to a customer or received from a vendor:</span></span>
<ul>
<li><span data-ttu-id="8d523-138">Potwierdzenie wystawienia zamówienia sprzedaży (M-15)*</span><span class="sxs-lookup"><span data-stu-id="8d523-138">Issue slip for sales order (M-15)*</span></span></li>
<li><span data-ttu-id="8d523-139">Dokument</span><span class="sxs-lookup"><span data-stu-id="8d523-139">Rmb.</span></span> <span data-ttu-id="8d523-140">KP/Zamówienie przyjęcia</span><span class="sxs-lookup"><span data-stu-id="8d523-140">slip/Receipt order</span></span></li>
<li><span data-ttu-id="8d523-141">Potwierdzenie wydania towarów dla zamówienia przeniesienia (M-15)*</span><span class="sxs-lookup"><span data-stu-id="8d523-141">Issue slip for transfer order (M-15)*</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8d523-142">\* Ten typ dokumentu jest dostępny tylko w firmach, których adresem podstawowym jest Rosja.</span><span class="sxs-lookup"><span data-stu-id="8d523-142">\* This document type is available only for legal entities that have their primary address in Russia.</span></span> <span data-ttu-id="8d523-143">W poniższej tabeli opisano pola znajdujące się na stronie **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="8d523-143">The following table describes the fields on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d523-144">Pole</span><span class="sxs-lookup"><span data-stu-id="8d523-144">Field</span></span></th>
<th><span data-ttu-id="8d523-145">opis</span><span class="sxs-lookup"><span data-stu-id="8d523-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8d523-146">Pozycja</span><span class="sxs-lookup"><span data-stu-id="8d523-146">Position</span></span></td>
<td><span data-ttu-id="8d523-147">Wybór tytułu stanowiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="8d523-147">Select the signer’s post title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-148">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="8d523-148">Name</span></span></td>
<td><span data-ttu-id="8d523-149">Wybór imienia i nazwiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="8d523-149">Select the signer’s name.</span></span> <span data-ttu-id="8d523-150">Imiona i nazwiska na liście pochodzą z tabeli Kontakty lub tabeli Pracownicy, w zależności od typu osoby podpisującej (tzn. w zależności od tego, czy jest zaznaczone pole wyboru <strong>Nasz</strong>).</span><span class="sxs-lookup"><span data-stu-id="8d523-150">The names in the list come from either the Contacts table or the Employees table, depending on the type of signer (that is, depending on whether the <strong>Our</strong> check box is selected).</span></span> <span data-ttu-id="8d523-151">Jeśli imienia i nazwiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</span><span class="sxs-lookup"><span data-stu-id="8d523-151">If the signer's name isn't in the list, manually enter the signer’s full name.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d523-152">Stanowisko</span><span class="sxs-lookup"><span data-stu-id="8d523-152">Job title</span></span></td>
<td><span data-ttu-id="8d523-153">Wybór stanowiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="8d523-153">Select the signer’s job title.</span></span> <span data-ttu-id="8d523-154">Jeśli stanowiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</span><span class="sxs-lookup"><span data-stu-id="8d523-154">If the signer’s title isn't in the list, manually enter the signer’s title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-155">Kod konta</span><span class="sxs-lookup"><span data-stu-id="8d523-155">Account code</span></span></td>
<td><span data-ttu-id="8d523-156">Określanie, czy osoba podpisująca może podpisywać wszystkie dokumenty wybranego typu, czy tylko dokumenty dotyczące określonego odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="8d523-156">Select whether the signer can sign all documents of the selected document type, or only documents for a specific customer or vendor.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d523-157">Relacja konta</span><span class="sxs-lookup"><span data-stu-id="8d523-157">Account relation</span></span></td>
<td><span data-ttu-id="8d523-158">Wybór konta odbiorcy lub dostawcy związanego z kodem wybranego konta.</span><span class="sxs-lookup"><span data-stu-id="8d523-158">Select the customer or vendor account that is related to the selected account code.</span></span> <span data-ttu-id="8d523-159">To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Kod konta</strong> zaznaczysz wartość <strong>Rekord</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d523-159">This field is available only if you select <strong>Record</strong> in the <strong>Account code</strong> field.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-160">Nasz</span><span class="sxs-lookup"><span data-stu-id="8d523-160">Our</span></span></td>
<td><span data-ttu-id="8d523-161">Zaznaczone pole wyboru wskazuje, że stanowisko jest wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="8d523-161">A selected check box indicates that the position is internal.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d523-162">Powiązanie z magazynem</span><span class="sxs-lookup"><span data-stu-id="8d523-162">Association with warehouse</span></span></td>
<td><span data-ttu-id="8d523-163">Określanie, czy osoba podpisująca jest przypisana do wszystkich magazynów, czy tylko do określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="8d523-163">Select whether the signer is assigned to all warehouses or only a specific warehouse.</span></span> <span data-ttu-id="8d523-164">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="8d523-164">The following options are available:</span></span>
<ul>
<li><span data-ttu-id="8d523-165"><strong>Wszystko</strong> — osoba podpisująca jest przypisana do wszystkich magazynów.</span><span class="sxs-lookup"><span data-stu-id="8d523-165"><strong>All</strong> – The signer is assigned to all warehouses.</span></span></li>
<li><span data-ttu-id="8d523-166"><strong>Rekord</strong> — osoba podpisująca jest przypisana do określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="8d523-166"><strong>Record</strong> – The signer is assigned to a specific warehouse.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d523-167">Magazyn</span><span class="sxs-lookup"><span data-stu-id="8d523-167">Warehouse</span></span></td>
<td><span data-ttu-id="8d523-168">Wybór kodu magazynu odpowiadającego magazynowi, do którego jest przypisana osoba podpisująca.</span><span class="sxs-lookup"><span data-stu-id="8d523-168">Select the warehouse code that corresponds to the warehouse that the signer is assigned to.</span></span> <span data-ttu-id="8d523-169">To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Powiązanie z magazynem</strong> zaznaczysz wartość <strong>Rekord</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d523-169">This field is available only if you select <strong>Record</strong> in the <strong>Association with warehouse</strong> field.</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a><span data-ttu-id="8d523-170">Konfigurowanie kodu numeracji danych urzędowych</span><span class="sxs-lookup"><span data-stu-id="8d523-170">Set up a number sequence code for officials</span></span>
<span data-ttu-id="8d523-171">Danym urzędowym można przypisać kod numeracji. Służy do tego sekcja **Sekwencje identyfikatorów** na stronie **Firmy**.</span><span class="sxs-lookup"><span data-stu-id="8d523-171">You can assign a number sequence code for officials in the **Number sequences** section of the **Legal entities** page.</span></span> <span data-ttu-id="8d523-172">Wybierz kod numeracji dla odwołania **Dane urzędowe — identyfikator sesji**.</span><span class="sxs-lookup"><span data-stu-id="8d523-172">Select a number sequence code for the **Officials session ID** reference.</span></span>

## <a name="modify-signers-in-primary-documents"></a><span data-ttu-id="8d523-173">Modyfikowanie osób podpisujących w głównych dokumentach</span><span class="sxs-lookup"><span data-stu-id="8d523-173">Modify signers in primary documents</span></span>
<span data-ttu-id="8d523-174">Funkcjonalność danych urzędowych pokazuje domyślne predefiniowane osoby podpisujące z tabeli Dane urzędowe.</span><span class="sxs-lookup"><span data-stu-id="8d523-174">The Officials functionality shows the default predefined signers from the Officials table.</span></span> <span data-ttu-id="8d523-175">Na stronie **Księgowanie faktury** na karcie **Dane urzędowe** można modyfikować imiona i nazwiska oraz tytuły osób podpisujących główne dokumenty następujących typów:</span><span class="sxs-lookup"><span data-stu-id="8d523-175">On the **Posting invoice** page, on the **Officials** tab, you can modify a signer’s name and title on the primary document for the following document types:</span></span>

-   <span data-ttu-id="8d523-176">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="8d523-176">Customer invoice</span></span>
-   <span data-ttu-id="8d523-177">Faktura dostawcy</span><span class="sxs-lookup"><span data-stu-id="8d523-177">Vendor invoice</span></span>
-   <span data-ttu-id="8d523-178">Wyślij zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="8d523-178">Ship transfer order</span></span>
-   <span data-ttu-id="8d523-179">Zamówienie gotówkowe</span><span class="sxs-lookup"><span data-stu-id="8d523-179">Cash order</span></span>

<span data-ttu-id="8d523-180">**Uwaga:** Po zaksięgowaniu dokumentu danych urzędowych nie można edytować.</span><span class="sxs-lookup"><span data-stu-id="8d523-180">**Note:** After a document is posted, officials can't be edited.</span></span>




