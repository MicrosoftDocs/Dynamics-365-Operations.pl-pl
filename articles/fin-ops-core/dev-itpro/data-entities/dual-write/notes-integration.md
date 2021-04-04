---
title: Integracja z notatkami
description: W tym temacie opisano integrację danych notatek w trybie zapisu podwójnego.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 221be52b4d66aaa47f9a1919d5d0b9f8459b7ff9
ms.sourcegitcommit: db9b35ce6968cad8874b3c13d4c02d84e2617c8b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/11/2021
ms.locfileid: "5577613"
---
# <a name="note-integration"></a><span data-ttu-id="d4ffb-103">Integracja z notatkami</span><span class="sxs-lookup"><span data-stu-id="d4ffb-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d4ffb-104">Podczas procesów biznesowych użytkownicy Microsoft Dynamics 365 często zbierają informacje o swoich klientach.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="d4ffb-105">Te informacje są rejestrowane jako działania i notatki.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="d4ffb-106">W tym temacie opisano integrację danych notatek w trybie zapisu podwójnego.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="d4ffb-107">Informacje o odbiorcy można sklasyfikować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d4ffb-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="d4ffb-108">**Informacje przydatne w działaniu, które użytkownik Dynamics 365 obsługuje w imieniu klienta** – Na przykład Contoso (użytkownik Dynamics 365) prowadzi teleturniej.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="d4ffb-109">Jeden z klientów firmy Contoso (klient) chce wziąć udział w teleturnieju.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="d4ffb-110">Klient prosi pracownika firmy Contoso o zarezerwowanie dla niego miejsca w teleturnieju.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="d4ffb-111">Rezerwacja następuje w kalendarzu uczestnika zdarzenia firmy Contoso.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="d4ffb-112">**Informacje przydatne dla użytkownika Dynamics 365** – Na przykład klient, który kupuje urządzenie Surface, wprowadza specjalne instrukcje, które wskazują, że urządzenie powinno zostać zapakowane na prezent przed dostawą.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="d4ffb-113">Te instrukcje to informacje umożliwiające wykonanie czynności, które powinien obsługiwać pracownik firmy Contoso odpowiedzialny za pakowanie.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="d4ffb-114">**Informacje niepodlegające działaniu** – Na przykład klient odwiedza sklep Contoso i podczas rozmowy ze współpracownikiem wyraża zainteresowanie grami i akcesoriami do gier *Halo*.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="d4ffb-115">Pracownik sklepu odnotowuje te informacje.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="d4ffb-116">Następnie aparat rekomendacji produktów używa go do sporządzania rekomendacji dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="d4ffb-117">Na ogół informacje dotyczące akcji są przechwytywane jako *działania* w aplikacjach Finance and Operations i aplikacjach dotyczącychrelacji z klientami.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="d4ffb-118">Na ogół informacje nie podlegające akcjom są przechwytywane jako *notatki* w aplikacjach Finance and Operations i jako *adnotacje* w aplikacjach dotyczących relacji z klientami.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="d4ffb-119">Chociaż notatki są przeznaczone dla informacji niepodlegających działaniu, aplikacje nie uniemożliwiają ich używania do przechowywania i obsługi informacji, które można wykonać, jeśli chcesz ich używać w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="d4ffb-120">Firma Microsoft obecnie udostępnia funkcje integracji notatek.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="d4ffb-121">(Funkcjonalność integracji działań zostanie udostępniona później). Integracja notatek jest dostępna dla klientów, dostawców, zamówień sprzedaży i zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="d4ffb-122">Utwórz notatkę w aplikacji angażującej klientów</span><span class="sxs-lookup"><span data-stu-id="d4ffb-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="d4ffb-123">Aby utworzyć notatkę w aplikacji angażującej klientów, a następnie zsynchronizować ją z aplikacją Finance and Operations, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="d4ffb-124">W aplikacji dotyczącej relacji z klientami otwórz rekord konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="d4ffb-125">W okienku **Osi czasu** wybierz znak plus (**+**), a następnie wybierz pozycję **Notatka**, aby utworzyć notatkę.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Utwórz notatkę w aplikacji angażującej klientów](media/notes-ce-1.png)

3. <span data-ttu-id="d4ffb-127">Wprowadź tytuł i opis, a następnie wybierz opcję **Dodaj notatkę**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Wprowadzenie tytułu i opisu](media/notes-ce-2.png)

    <span data-ttu-id="d4ffb-129">Nowa notatka zostanie dodana do osi czasu dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-129">The new note is added to the customer timeline.</span></span>

    ![Nowa notatka na osi czasu dla odbiorcy](media/notes-ce-3.png)

4. <span data-ttu-id="d4ffb-131">Zaloguj się do aplikacji Finance and Operations i otwórz ten sam rekord odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="d4ffb-132">Zwróć uwagę, że przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu wskazuje, że rekord ma załącznik.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Powiadomienie o załączniku](media/notes-ce-4.png)

5. <span data-ttu-id="d4ffb-134">Wybierz przycisk **Załączniki**, aby otworzyć stronę **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="d4ffb-135">Powinieneś znaleźć notatkę, którą utworzyłeś w aplikacji do obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Notatka z aplikacji angażującej klienta](media/notes-ce-5.png)

<span data-ttu-id="d4ffb-137">Wszelkie aktualizacje notatki są synchronizowane między aplikacją Finance and Operations a aplikacją do obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="d4ffb-138">Utwórz notatkę w aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4ffb-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="d4ffb-139">Możesz również utworzyć notatkę w aplikacji Finance and Operations, która zostanie zsynchronizowana z aplikacją do obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="d4ffb-140">Aby utworzyć notatkę w aplikacji Finance and Operations, a następnie zsynchronizować ją z aplikacją angażującą klientów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="d4ffb-141">W aplikacji Finance and Operations, na stronie **Załącznik** i wybierz pozycję **Nowa** \> **Notatka**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Utwórz notatkę w aplikacji Finance and Operations](media/notes-fo-1.png)

2. <span data-ttu-id="d4ffb-143">Wprowadź tytuł i krótki zestaw instrukcji, a następnie wybierz polecenie **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Wprowadzanie tytułu i instrukcji](media/notes-fo-2.png)

3. <span data-ttu-id="d4ffb-145">Zaktualizuj rekord w aplikacji angażującej klienta.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="d4ffb-146">Nowa notatka powinna znaleźć się na osi czasu.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-146">You should find the new note on the timeline.</span></span>

    ![Nowa notatka na osi czasu w aplikacji do obsługi klienta](media/notes-fo-3.png)

<span data-ttu-id="d4ffb-148">Notatkę można sklasyfikować jako wewnętrzną lub zewnętrzną.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="d4ffb-149">W aplikacji Finance and Operations, na stronie **Załączniki** otwórz notatkę, a następnie w polu **Ograniczenie** wybierz pozycję **Wewnętrzna** lub **Zewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Pole ograniczenia](media/notes-fo-4.png)

<span data-ttu-id="d4ffb-151">Można również utworzyć adres URL.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-151">You can also create a URL.</span></span>

1. <span data-ttu-id="d4ffb-152">W aplikacji Finance and Operations, na stronie **Załącznik** i wybierz pozycję **Nowa** \> **Adres URL**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="d4ffb-153">Wprowadź tytuł i adres URL.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="d4ffb-154">W polu **Ograniczenie** wybierz opcję **Wewnętrzna** lub **Zewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Utwórz adres URL w aplikacji Finance and Operations](media/notes-fo-5.png)

4. <span data-ttu-id="d4ffb-156">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-156">Select **Save**.</span></span>

    <span data-ttu-id="d4ffb-157">Ponieważ aplikacje angażujące klientów nie mają typu adresu URL, adres URL jest zintegrowany z podwójnym zapisem jako notatka.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL pojawiający się jako notatka w aplikacji budującej zaangażowanie klientów](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="d4ffb-159">Załączniki plików nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="d4ffb-160">Szablony</span><span class="sxs-lookup"><span data-stu-id="d4ffb-160">Templates</span></span>

<span data-ttu-id="d4ffb-161">Integracja notatek obejmuje zbiór map tabel, które współpracują podczas interakcji danych, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="d4ffb-162">Aplikacja Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4ffb-162">Finance and Operations app</span></span> | <span data-ttu-id="d4ffb-163">Aplikacja Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d4ffb-163">Customer engagement app</span></span> | <span data-ttu-id="d4ffb-164">opis</span><span class="sxs-lookup"><span data-stu-id="d4ffb-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="d4ffb-165">Załączniki odbiorcy</span><span class="sxs-lookup"><span data-stu-id="d4ffb-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="d4ffb-166">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="d4ffb-166">Annotations</span></span> | <span data-ttu-id="d4ffb-167">Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji specyficznych dla klienta (zarówno dla organizacji, jak i osób).</span><span class="sxs-lookup"><span data-stu-id="d4ffb-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="d4ffb-168">Załączniki dokumentów dostawców</span><span class="sxs-lookup"><span data-stu-id="d4ffb-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="d4ffb-169">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="d4ffb-169">Annotations</span></span> | <span data-ttu-id="d4ffb-170">Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji specyficznych dla dostawcy (zarówno dla organizacji, jak i osób).</span><span class="sxs-lookup"><span data-stu-id="d4ffb-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="d4ffb-171">Załączniki dokumentu nagłówka zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d4ffb-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="d4ffb-172">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="d4ffb-172">Annotations</span></span> | <span data-ttu-id="d4ffb-173">Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji dotyczących zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="d4ffb-174">Załączniki dokumentu nagłówka zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="d4ffb-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="d4ffb-175">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="d4ffb-175">Annotations</span></span> | <span data-ttu-id="d4ffb-176">Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji dotyczących zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="d4ffb-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="d4ffb-177">Aby uzyskać więcej informacji, zobacz [Odniesienie do mapowania z podwójnym zapisem](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d4ffb-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
