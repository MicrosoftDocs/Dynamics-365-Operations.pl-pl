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
ms.search.scope: Core, Operations
ms.custom: 263464
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: df924487c02ee9c7246ab9f12719382459634e98
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-signers-for-print-forms"></a><span data-ttu-id="04fe9-103">Konfigurowanie osób podpisujących drukowane formularze</span><span class="sxs-lookup"><span data-stu-id="04fe9-103">Set up signers for print forms</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="04fe9-104">Dla firm w Czechach, Estonii, na Węgrzech, Litwie, Łotwie, w Polsce i Rosji można skonfigurować osoby podpisujące oraz tytuły dla odbiorców i dostawców, którzy drukują dokumenty, takie jak faktury i zamówienia gotówkowe.</span><span class="sxs-lookup"><span data-stu-id="04fe9-104">For legal entities in Czech Republic, Estonia, Hungary, Lithuania, Latvia, Poland, and Russia, you can set up signers and titles for customers and vendors that print documents such as invoices and cash orders.</span></span>

<a name="set-up-default-values"></a><span data-ttu-id="04fe9-105">Konfigurowanie wartości domyślnych</span><span class="sxs-lookup"><span data-stu-id="04fe9-105">Set up default values</span></span>
---------------------

<span data-ttu-id="04fe9-106">Aby skonfigurować osoby podpisujące dokumenty drukowane przez firmę, należy użyć strony **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="04fe9-106">To set up signers for the documents that a company prints, use the **Officials** page.</span></span> <span data-ttu-id="04fe9-107">Można skonfigurować osoby podpisujące i ich tytuły zarówno dla firmy, jak i dla odbiorców lub dostawców, w zależności od typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="04fe9-107">You can set up signers and their titles both for the company and for customers or vendors, depending on the document type.</span></span> <span data-ttu-id="04fe9-108">W poniższej tabeli opisano karty znajdujące się na stronie **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="04fe9-108">The following table describes the tabs on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04fe9-109">Karta</span><span class="sxs-lookup"><span data-stu-id="04fe9-109">Tab</span></span></th>
<th><span data-ttu-id="04fe9-110">opis</span><span class="sxs-lookup"><span data-stu-id="04fe9-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="04fe9-111">Ogólne</span><span class="sxs-lookup"><span data-stu-id="04fe9-111">General</span></span></td>
<td><span data-ttu-id="04fe9-112">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących (dyrektor i główny księgowy), które mogą podpisywać drukowane dokumenty wszystkich typów.</span><span class="sxs-lookup"><span data-stu-id="04fe9-112">Add positions and related information for signers (Director and Chief accountant) who can sign print documents of all types.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-113">Księga</span><span class="sxs-lookup"><span data-stu-id="04fe9-113">Ledger</span></span></td>
<td><span data-ttu-id="04fe9-114">Dodawanie stanowiska i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące wewnętrzne dokumenty finansowe związane z przepływem środków pieniężnych:</span><span class="sxs-lookup"><span data-stu-id="04fe9-114">Add the position and related information for signers who can sign the following internal financial documents that are related to cash flow:</span></span>
<ul>
<li><span data-ttu-id="04fe9-115">Dokumenty kasowe</span><span class="sxs-lookup"><span data-stu-id="04fe9-115">Cash slips</span></span></li>
<li><span data-ttu-id="04fe9-116">Raport zaliczek</span><span class="sxs-lookup"><span data-stu-id="04fe9-116">Advance report</span></span></li>
<li><span data-ttu-id="04fe9-117">Strona księgi kasowej</span><span class="sxs-lookup"><span data-stu-id="04fe9-117">Page of cash book</span></span></li>
<li><span data-ttu-id="04fe9-118">Wyciąg kasowy zliczania</span><span class="sxs-lookup"><span data-stu-id="04fe9-118">Count statement</span></span></li>
<li><span data-ttu-id="04fe9-119">Odroczenia*</span><span class="sxs-lookup"><span data-stu-id="04fe9-119">Deferrals*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="04fe9-120">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="04fe9-120">Sales orders</span></span></td>
<td><span data-ttu-id="04fe9-121">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty wychodzące związane z odbiorcami:</span><span class="sxs-lookup"><span data-stu-id="04fe9-121">Add positions and related information for signers who can sign the following outgoing primary documents that are related to customers:</span></span>
<ul>
<li><span data-ttu-id="04fe9-122">Faktura do zapłaty*</span><span class="sxs-lookup"><span data-stu-id="04fe9-122">Invoice for payment*</span></span></li>
<li><span data-ttu-id="04fe9-123">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="04fe9-123">Invoice</span></span></li>
<li><span data-ttu-id="04fe9-124">Dokument faktury*</span><span class="sxs-lookup"><span data-stu-id="04fe9-124">Facture*</span></span></li>
<li><span data-ttu-id="04fe9-125">Faktura — faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="04fe9-125">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="04fe9-126">Dokument faktury — faktura korygująca*</span><span class="sxs-lookup"><span data-stu-id="04fe9-126">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="04fe9-127">Dokument faktury transakcji podatku (klient)*</span><span class="sxs-lookup"><span data-stu-id="04fe9-127">Tax transaction facture (client)*</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-128">Zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="04fe9-128">Purchase orders</span></span></td>
<td><span data-ttu-id="04fe9-129">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące główne dokumenty przychodzące związane z dostawcami:</span><span class="sxs-lookup"><span data-stu-id="04fe9-129">Add positions and related information for signers who can sign the following incoming primary documents that are related to vendors:</span></span>
<ul>
<li><span data-ttu-id="04fe9-130">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="04fe9-130">Invoice</span></span></li>
<li><span data-ttu-id="04fe9-131">Dokument faktury*</span><span class="sxs-lookup"><span data-stu-id="04fe9-131">Facture*</span></span></li>
<li><span data-ttu-id="04fe9-132">Faktura — faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="04fe9-132">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="04fe9-133">Dokument faktury — faktura korygująca*</span><span class="sxs-lookup"><span data-stu-id="04fe9-133">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="04fe9-134">Faktura do zapłaty*</span><span class="sxs-lookup"><span data-stu-id="04fe9-134">Invoice for payment*</span></span></li>
<li><span data-ttu-id="04fe9-135">Dokument faktury transakcji podatku (dostawca)*</span><span class="sxs-lookup"><span data-stu-id="04fe9-135">Tax transaction facture (vendor)*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="04fe9-136">Zarządzanie pozycjami magazynowymi</span><span class="sxs-lookup"><span data-stu-id="04fe9-136">Inventory item management</span></span></td>
<td><span data-ttu-id="04fe9-137">Dodawanie stanowisk i pokrewnych informacji o osobach podpisujących, które mogą podpisywać następujące dokumenty magazynowe, gdy materialne środki trwałe są wydawane do odbiorcy lub przyjmowane od dostawcy:</span><span class="sxs-lookup"><span data-stu-id="04fe9-137">Add positions and related information for signers who can sign the following warehouse documents when tangible assets are issued to a customer or received from a vendor:</span></span>
<ul>
<li><span data-ttu-id="04fe9-138">Potwierdzenie wystawienia zamówienia sprzedaży (M-15)*</span><span class="sxs-lookup"><span data-stu-id="04fe9-138">Issue slip for sales order (M-15)*</span></span></li>
<li><span data-ttu-id="04fe9-139">Dokument</span><span class="sxs-lookup"><span data-stu-id="04fe9-139">Rmb.</span></span> <span data-ttu-id="04fe9-140">KP/Zamówienie przyjęcia</span><span class="sxs-lookup"><span data-stu-id="04fe9-140">slip/Receipt order</span></span></li>
<li><span data-ttu-id="04fe9-141">Potwierdzenie wydania towarów dla zamówienia przeniesienia (M-15)*</span><span class="sxs-lookup"><span data-stu-id="04fe9-141">Issue slip for transfer order (M-15)*</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04fe9-142">\* Ten typ dokumentu jest dostępny tylko w firmach, których adresem podstawowym jest Rosja.</span><span class="sxs-lookup"><span data-stu-id="04fe9-142">\* This document type is available only for legal entities that have their primary address in Russia.</span></span> <span data-ttu-id="04fe9-143">W poniższej tabeli opisano pola znajdujące się na stronie **Dane urzędowe**.</span><span class="sxs-lookup"><span data-stu-id="04fe9-143">The following table describes the fields on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04fe9-144">Pole</span><span class="sxs-lookup"><span data-stu-id="04fe9-144">Field</span></span></th>
<th><span data-ttu-id="04fe9-145">opis</span><span class="sxs-lookup"><span data-stu-id="04fe9-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="04fe9-146">Pozycja</span><span class="sxs-lookup"><span data-stu-id="04fe9-146">Position</span></span></td>
<td><span data-ttu-id="04fe9-147">Wybór tytułu stanowiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="04fe9-147">Select the signer’s post title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-148">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="04fe9-148">Name</span></span></td>
<td><span data-ttu-id="04fe9-149">Wybór imienia i nazwiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="04fe9-149">Select the signer’s name.</span></span> <span data-ttu-id="04fe9-150">Imiona i nazwiska na liście pochodzą z tabeli Kontakty lub tabeli Pracownicy, w zależności od typu osoby podpisującej (tzn. w zależności od tego, czy jest zaznaczone pole wyboru <strong>Nasz</strong>).</span><span class="sxs-lookup"><span data-stu-id="04fe9-150">The names in the list come from either the Contacts table or the Employees table, depending on the type of signer (that is, depending on whether the <strong>Our</strong> check box is selected).</span></span> <span data-ttu-id="04fe9-151">Jeśli imienia i nazwiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</span><span class="sxs-lookup"><span data-stu-id="04fe9-151">If the signer's name isn't in the list, manually enter the signer’s full name.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="04fe9-152">Stanowisko</span><span class="sxs-lookup"><span data-stu-id="04fe9-152">Job title</span></span></td>
<td><span data-ttu-id="04fe9-153">Wybór stanowiska osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="04fe9-153">Select the signer’s job title.</span></span> <span data-ttu-id="04fe9-154">Jeśli stanowiska osoby podpisującej nie ma na liście, należy ręcznie wprowadzić tę informację.</span><span class="sxs-lookup"><span data-stu-id="04fe9-154">If the signer’s title isn't in the list, manually enter the signer’s title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-155">Kod konta</span><span class="sxs-lookup"><span data-stu-id="04fe9-155">Account code</span></span></td>
<td><span data-ttu-id="04fe9-156">Określanie, czy osoba podpisująca może podpisywać wszystkie dokumenty wybranego typu, czy tylko dokumenty dotyczące określonego odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="04fe9-156">Select whether the signer can sign all documents of the selected document type, or only documents for a specific customer or vendor.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="04fe9-157">Relacja konta</span><span class="sxs-lookup"><span data-stu-id="04fe9-157">Account relation</span></span></td>
<td><span data-ttu-id="04fe9-158">Wybór konta odbiorcy lub dostawcy związanego z kodem wybranego konta.</span><span class="sxs-lookup"><span data-stu-id="04fe9-158">Select the customer or vendor account that is related to the selected account code.</span></span> <span data-ttu-id="04fe9-159">To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Kod konta</strong> zaznaczysz wartość <strong>Rekord</strong>.</span><span class="sxs-lookup"><span data-stu-id="04fe9-159">This field is available only if you select <strong>Record</strong> in the <strong>Account code</strong> field.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-160">Nasz</span><span class="sxs-lookup"><span data-stu-id="04fe9-160">Our</span></span></td>
<td><span data-ttu-id="04fe9-161">Zaznaczone pole wyboru wskazuje, że stanowisko jest wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="04fe9-161">A selected check box indicates that the position is internal.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="04fe9-162">Powiązanie z magazynem</span><span class="sxs-lookup"><span data-stu-id="04fe9-162">Association with warehouse</span></span></td>
<td><span data-ttu-id="04fe9-163">Określanie, czy osoba podpisująca jest przypisana do wszystkich magazynów, czy tylko do określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="04fe9-163">Select whether the signer is assigned to all warehouses or only a specific warehouse.</span></span> <span data-ttu-id="04fe9-164">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="04fe9-164">The following options are available:</span></span>
<ul>
<li><span data-ttu-id="04fe9-165"><strong>Wszystko</strong> — osoba podpisująca jest przypisana do wszystkich magazynów.</span><span class="sxs-lookup"><span data-stu-id="04fe9-165"><strong>All</strong> – The signer is assigned to all warehouses.</span></span></li>
<li><span data-ttu-id="04fe9-166"><strong>Rekord</strong> — osoba podpisująca jest przypisana do określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="04fe9-166"><strong>Record</strong> – The signer is assigned to a specific warehouse.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="04fe9-167">Magazyn</span><span class="sxs-lookup"><span data-stu-id="04fe9-167">Warehouse</span></span></td>
<td><span data-ttu-id="04fe9-168">Wybór kodu magazynu odpowiadającego magazynowi, do którego jest przypisana osoba podpisująca.</span><span class="sxs-lookup"><span data-stu-id="04fe9-168">Select the warehouse code that corresponds to the warehouse that the signer is assigned to.</span></span> <span data-ttu-id="04fe9-169">To pole to jest dostępne tylko w przypadku, gdy w polu <strong>Powiązanie z magazynem</strong> zaznaczysz wartość <strong>Rekord</strong>.</span><span class="sxs-lookup"><span data-stu-id="04fe9-169">This field is available only if you select <strong>Record</strong> in the <strong>Association with warehouse</strong> field.</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a><span data-ttu-id="04fe9-170">Konfigurowanie kodu numeracji danych urzędowych</span><span class="sxs-lookup"><span data-stu-id="04fe9-170">Set up a number sequence code for officials</span></span>
<span data-ttu-id="04fe9-171">Danym urzędowym można przypisać kod numeracji. Służy do tego sekcja **Sekwencje identyfikatorów** na stronie **Firmy**.</span><span class="sxs-lookup"><span data-stu-id="04fe9-171">You can assign a number sequence code for officials in the **Number sequences** section of the **Legal entities** page.</span></span> <span data-ttu-id="04fe9-172">Wybierz kod numeracji dla odwołania **Dane urzędowe — identyfikator sesji**.</span><span class="sxs-lookup"><span data-stu-id="04fe9-172">Select a number sequence code for the **Officials session ID** reference.</span></span>

## <a name="modify-signers-in-primary-documents"></a><span data-ttu-id="04fe9-173">Modyfikowanie osób podpisujących w głównych dokumentach</span><span class="sxs-lookup"><span data-stu-id="04fe9-173">Modify signers in primary documents</span></span>
<span data-ttu-id="04fe9-174">Funkcjonalność danych urzędowych pokazuje domyślne predefiniowane osoby podpisujące z tabeli Dane urzędowe.</span><span class="sxs-lookup"><span data-stu-id="04fe9-174">The Officials functionality shows the default predefined signers from the Officials table.</span></span> <span data-ttu-id="04fe9-175">Na stronie **Księgowanie faktury** na karcie **Dane urzędowe** można modyfikować imiona i nazwiska oraz tytuły osób podpisujących główne dokumenty następujących typów:</span><span class="sxs-lookup"><span data-stu-id="04fe9-175">On the **Posting invoice** page, on the **Officials** tab, you can modify a signer’s name and title on the primary document for the following document types:</span></span>

-   <span data-ttu-id="04fe9-176">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="04fe9-176">Customer invoice</span></span>
-   <span data-ttu-id="04fe9-177">Faktura dostawcy</span><span class="sxs-lookup"><span data-stu-id="04fe9-177">Vendor invoice</span></span>
-   <span data-ttu-id="04fe9-178">Wyślij zamówienie przeniesienia</span><span class="sxs-lookup"><span data-stu-id="04fe9-178">Ship transfer order</span></span>
-   <span data-ttu-id="04fe9-179">Zamówienie gotówkowe</span><span class="sxs-lookup"><span data-stu-id="04fe9-179">Cash order</span></span>

<span data-ttu-id="04fe9-180">**Uwaga:** Po zaksięgowaniu dokumentu danych urzędowych nie można edytować.</span><span class="sxs-lookup"><span data-stu-id="04fe9-180">**Note:** After a document is posted, officials can't be edited.</span></span>




