---
title: Szablony BOM
description: Szablon listy składowej (BOM) zawiera standardową listę składników przedmiotów serwisu, które są regularnie serwisowane.
author: ShylaThompson
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70b514aeed48180bb1b14be8b3d95d55d44d2ca8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824339"
---
# <a name="template-boms"></a><span data-ttu-id="713ba-103">Szablony BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="713ba-104">Szablon listy składowej (BOM) prezentuje standardową listę składników przedmiotów serwisu, które są regularnie serwisowane.</span><span class="sxs-lookup"><span data-stu-id="713ba-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="713ba-105">Składniki wymienione w szablonie BOM są niezależnymi podskładnikami przedmiotu serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="713ba-106">Gdy szablon BOM zostanie zastosowany do przedmiotu serwisu, można zachować spis podksładników, które zostały wymienione w przedmiocie serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="713ba-107">Aby zastosować szablon BOM do umowy serwisowej lub zlecenia serwisowego, należy go dołączyć do relacji przedmiotu serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="713ba-108">Do jednego przedmiotu serwisu można zastosować tylko jeden szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="713ba-109">Tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-109">Create a template BOM</span></span>

<span data-ttu-id="713ba-110">Poniższa tabela zawiera informacje o różnych metodach tworzenia szablonów BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="713ba-111">Metoda</span><span class="sxs-lookup"><span data-stu-id="713ba-111">Method</span></span></p></th>
<th><p><span data-ttu-id="713ba-112">opis</span><span class="sxs-lookup"><span data-stu-id="713ba-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="713ba-113">Produkcja</span><span class="sxs-lookup"><span data-stu-id="713ba-113">Production</span></span></p></td>
<td><p><span data-ttu-id="713ba-114">Szablon BOM bazuje na zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="713ba-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="713ba-115">Ta opcja jest odpowiednia tylko wtedy, gdy działasz w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="713ba-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="713ba-116">Zaleta jest taka, że masz aktualną, szczegółową listę składników tworzących towar.</span><span class="sxs-lookup"><span data-stu-id="713ba-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="713ba-117">Towar BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="713ba-118">Szablon BOM bazuje na BOM towaru.</span><span class="sxs-lookup"><span data-stu-id="713ba-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="713ba-119">BOM towaru, w przeciwieństwie do BOM produkcji, jest statyczną listą składników tworzących towar.</span><span class="sxs-lookup"><span data-stu-id="713ba-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="713ba-120">Istniejący szablon</span><span class="sxs-lookup"><span data-stu-id="713ba-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="713ba-121">Szablon bazuje na istniejącym szablonie BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="713ba-122">Ręczny</span><span class="sxs-lookup"><span data-stu-id="713ba-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="713ba-123">Jeśli wiadomo, jakie części są zazwyczaj wymieniane w przedmiocie serwisu, można ręcznie utworzyć szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="713ba-124">Ta metoda pomaga uzyskać pewność, że składniki umieszczone w szablonie odzwierciedlają faktyczne potrzeby miejsca pracy.</span><span class="sxs-lookup"><span data-stu-id="713ba-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="713ba-125">Stosowanie szablonu BOM do umowy serwisowej lub zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="713ba-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="713ba-126">Szablon BOM można zastosować do umowy serwisowej i/lub zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="713ba-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="713ba-127">Umowa serwisowa zazwyczaj dotyczy długoterminowej relacji z odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="713ba-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="713ba-128">Historia wymiany zarejestrowana w BOM serwisu zawiera dane, które są przydatne w umowie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="713ba-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="713ba-129">Można również zastosować szablon BOM do zlecenia serwisowego w celu rejestrowania historii czynności serwisowych wykonywanych na przedmiocie serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="713ba-130">Kopiowanie historii BOM serwisu</span><span class="sxs-lookup"><span data-stu-id="713ba-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="713ba-131">Historię wiersza BOM serwisu można kopiować między umowami serwisowymi.</span><span class="sxs-lookup"><span data-stu-id="713ba-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="713ba-132">Skopiowanie historii serwisu między umowami pomaga zachować rejestr wymiany części.</span><span class="sxs-lookup"><span data-stu-id="713ba-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="713ba-133">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="713ba-133">**Example**</span></span>

<span data-ttu-id="713ba-134">Powstała trzyletnia umowa serwisowa dotycząca serwisowania samochodu klienta.</span><span class="sxs-lookup"><span data-stu-id="713ba-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="713ba-135">W tym okresie odbiorca przyzwyczaił się do dobrej opieki serwisowej oferowanej przez firmę.</span><span class="sxs-lookup"><span data-stu-id="713ba-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="713ba-136">Z tego względu po wygaśnięciu umowy chce zawrzeć nową.</span><span class="sxs-lookup"><span data-stu-id="713ba-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="713ba-137">Teraz można wynegocjować dla firmy lepsze warunki.</span><span class="sxs-lookup"><span data-stu-id="713ba-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="713ba-138">Ponieważ rejestr wymienionych części może przydać się w przyszłości, kopiujesz historię BOM serwisu do nowej umowy.</span><span class="sxs-lookup"><span data-stu-id="713ba-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="713ba-139">Modyfikowanie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-139">Modify the template BOM</span></span>

<span data-ttu-id="713ba-140">Jeśli szablon BOM nie został dołączony do przedmiotu serwisu, można w nim modyfikować i usuwać wiersze.</span><span class="sxs-lookup"><span data-stu-id="713ba-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="713ba-141">Jeśli szablon BOM został dołączony do przedmiotu serwisu, można modyfikować tylko lokalną wersję BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="713ba-142">Aby skopiować konfigurację wersji lokalnej szablonu BOM, można utworzyć nowy szablon BOM oparty na wersji lokalnej.</span><span class="sxs-lookup"><span data-stu-id="713ba-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="713ba-143">Aby uzyskać więcej informacji, zobacz [Modyfikowanie BOM serwisu](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="713ba-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="713ba-144">Zastąpienie towaru w BOM można zarejestrować w wierszu BOM w konstruktorze BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="713ba-145">Opcjonalnie dla przedmiotu wymiany można utworzyć wiersz zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="713ba-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="713ba-146">Jeśli utworzysz wiersz zlecenia serwisowego, można wystawić fakturę za część zamienną.</span><span class="sxs-lookup"><span data-stu-id="713ba-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="713ba-147">Jeśli wiersz zlecenia serwisowego dotyczący wymiany nie zostanie utworzony, informacja o wymianie pozostanie zarejestrowana na potrzeby historii przedmiotu serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="713ba-148">Zmiana sposobu wyświetlania informacji w wierszu BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="713ba-149">Sposób wyświetlania informacji w wierszu BOM można zmieniać we wszystkich szablonach BOM oraz w BOM serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="713ba-150">Zmiany zostaną zastosowane do wszystkich szablonów BOM i BOM serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="713ba-151">Dotyczy to również tych, które są dołączone do przedmiotów serwisu.</span><span class="sxs-lookup"><span data-stu-id="713ba-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="713ba-152">Konfigurowanie numeracji szablonów BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="713ba-153">Aby korzystać z szablonów BOM, należy skonfigurować dwie numeracje.</span><span class="sxs-lookup"><span data-stu-id="713ba-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="713ba-154">Jedna z nich musi dotyczyć szablonu BOM, a druga numeru wiersza historii BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="713ba-155">Numeracje są używane do przydzielania identyfikatorów rekordom, które tego wymagają.</span><span class="sxs-lookup"><span data-stu-id="713ba-155">Number sequences are used to allocate identifiers to records that require them.</span></span> <span data-ttu-id="713ba-156">Zanim będzie można przypisać numerację do szablonu BOM lub numer wiersza historii BOM, należy skonfigurować kody numeracji.</span><span class="sxs-lookup"><span data-stu-id="713ba-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="713ba-157">Ustawienie sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="713ba-157">Set up number sequences</span></span>

1.  <span data-ttu-id="713ba-158">Na stronie listy **Sekwencje numerów** utwórz numerację dla szablonów BOM i numeru wiersza historii BOM.</span><span class="sxs-lookup"><span data-stu-id="713ba-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="713ba-159">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.</span><span class="sxs-lookup"><span data-stu-id="713ba-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="713ba-160">Kliknij przycisk **Sekwencje numerów**, a następnie wybierz kod numeracji dla odwołań do numeracji utworzonych w formularza **Sekwencje numerów**.</span><span class="sxs-lookup"><span data-stu-id="713ba-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="713ba-161">Zamknij formularz, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="713ba-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="713ba-162">Numer wiersza historii BOM jest używany przez system do skojarzenia transakcji w historii BOM z umową serwisową lub zleceniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="713ba-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="713ba-163">Numer nie jest wyświetlany w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="713ba-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="713ba-164">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="713ba-164">See also</span></span>

[<span data-ttu-id="713ba-165">Tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="713ba-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="713ba-166">Zarządzanie szablonami BOM w relacjach przedmiotów</span><span class="sxs-lookup"><span data-stu-id="713ba-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="713ba-167">Modyfikowanie BOM serwisu</span><span class="sxs-lookup"><span data-stu-id="713ba-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]