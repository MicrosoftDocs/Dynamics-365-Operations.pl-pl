---
title: Konfigurowanie zadań wykonywanych automatycznie w przepływie pracy
description: W tym temacie wyjaśniono sposób konfigurowania właściwości zadania wykonywanego automatycznie.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a9f37228beedafa085987668d5c89b06c6c9d61
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "365116"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="4abfe-103">Konfigurowanie zadań wykonywanych automatycznie w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="4abfe-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4abfe-104">W tym temacie wyjaśniono sposób konfigurowania właściwości zadania wykonywanego automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4abfe-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="4abfe-105">Aby skonfigurować zadanie wykonywane automatycznie, w edytorze przepływu pracy kliknij zadanie prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="4abfe-106">Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości zadania wykonywanego automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4abfe-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="4abfe-107">Nadawanie nazwy zadaniu</span><span class="sxs-lookup"><span data-stu-id="4abfe-107">Name the task</span></span>

<span data-ttu-id="4abfe-108">Wykonaj następujące kroki, aby wprowadzić nazwę zadania wykonywanego automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4abfe-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="4abfe-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4abfe-110">W polu **Nazwa** wprowadź unikatową nazwę zadania.</span><span class="sxs-lookup"><span data-stu-id="4abfe-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="4abfe-111">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="4abfe-111">Specify when notifications are sent</span></span>

<span data-ttu-id="4abfe-112">Można wysyłać powiadomienia do odpowiednich osób po ponownym uruchomieniu lub anulowaniu zadania wykonywanego automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4abfe-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="4abfe-113">Wykonaj następujące kroki, aby określić, kiedy i do kogo są one wysyłane.</span><span class="sxs-lookup"><span data-stu-id="4abfe-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="4abfe-114">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="4abfe-115">Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="4abfe-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="4abfe-116">**Wykonanie** — powiadomienia są wysyłane po wykonaniu zadania.</span><span class="sxs-lookup"><span data-stu-id="4abfe-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="4abfe-117">**Anulowano** — powiadomienia są wysyłane po anulowaniu zadania.</span><span class="sxs-lookup"><span data-stu-id="4abfe-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="4abfe-118">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="4abfe-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="4abfe-119">Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="4abfe-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="4abfe-120">Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="4abfe-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="4abfe-121">Podczas wyświetlania powiadomienia użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="4abfe-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="4abfe-122">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="4abfe-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4abfe-123">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="4abfe-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4abfe-124">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4abfe-125">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="4abfe-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4abfe-126">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-126">Click **Insert**.</span></span>

6. <span data-ttu-id="4abfe-127">Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="4abfe-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="4abfe-128">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="4abfe-129">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4abfe-130">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="4abfe-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4abfe-131">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="4abfe-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4abfe-132">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.</span><span class="sxs-lookup"><span data-stu-id="4abfe-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="4abfe-133">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="4abfe-133">Click **Close**.</span></span>

7. <span data-ttu-id="4abfe-134">Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="4abfe-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="4abfe-135">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.</span><span class="sxs-lookup"><span data-stu-id="4abfe-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4abfe-136">Opcja</span><span class="sxs-lookup"><span data-stu-id="4abfe-136">Option</span></span></th>
    <th><span data-ttu-id="4abfe-137">Adresaci powiadomień</span><span class="sxs-lookup"><span data-stu-id="4abfe-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="4abfe-138">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="4abfe-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4abfe-139">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="4abfe-139">Participant</span></span></td>
    <td><span data-ttu-id="4abfe-140">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="4abfe-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4abfe-141">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="4abfe-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="4abfe-142">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="4abfe-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4abfe-143">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="4abfe-143">Workflow user</span></span></td>
    <td><span data-ttu-id="4abfe-144">Użytkownicy uczestniczący w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="4abfe-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4abfe-145">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="4abfe-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4abfe-146">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="4abfe-146">User</span></span></td>
    <td><span data-ttu-id="4abfe-147">Określeni użytkownicy Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4abfe-147">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4abfe-148">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="4abfe-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4abfe-149">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4abfe-149">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="4abfe-150">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="4abfe-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="4abfe-151">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="4abfe-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>
