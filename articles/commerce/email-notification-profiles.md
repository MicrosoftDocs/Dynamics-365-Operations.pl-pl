---
title: Konfigurowanie powiadomień pocztą e-mail
description: W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 320f21916a5f451ebf4f21e0075017a121ba6d6a
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057621"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="21a38-103">Konfigurowanie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="21a38-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="21a38-104">W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="21a38-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="21a38-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="21a38-105">Overview</span></span>

<span data-ttu-id="21a38-106">Przed utworzeniem kanałów należy skonfigurować profil, aby zapewnić możliwość wysyłania powiadomień pocztą e-mail dla różnych zdarzeń, takich jak tworzenie zamówień, stan wysyłki zamówienia i niepowodzenia płatności.</span><span class="sxs-lookup"><span data-stu-id="21a38-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="21a38-107">Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).</span><span class="sxs-lookup"><span data-stu-id="21a38-107">For additional email configuration information, see [Configure and send email](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="21a38-108">Tworzenie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="21a38-108">Create an email notification profile</span></span>

<span data-ttu-id="21a38-109">Aby utworzyć profil powiadomień e-mail, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="21a38-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="21a38-110">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="21a38-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="21a38-111">W okienku akcji kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="21a38-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="21a38-112">W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.</span><span class="sxs-lookup"><span data-stu-id="21a38-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="21a38-113">W polu **Opis** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="21a38-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="21a38-114">Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="21a38-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="21a38-115">Tworzenie szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="21a38-115">Create an email template</span></span>

<span data-ttu-id="21a38-116">Aby można było utworzyć powiadomienie e-mail, należy utworzyć szablon wiadomości e-mail organizacji zawierający informacje o adresach e-mail nadawców oraz szablon wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="21a38-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="21a38-117">Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="21a38-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="21a38-118">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Parametry sieci sprzedaży \> Szablony e-maili organizacji**.</span><span class="sxs-lookup"><span data-stu-id="21a38-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="21a38-119">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="21a38-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="21a38-120">W polu **Identyfikator e-mail** wprowadź identyfikator ułatwiający identyfikację tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="21a38-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="21a38-121">W polu **Nazwa wysyłającego** wprowadź nazwę wysyłającego.</span><span class="sxs-lookup"><span data-stu-id="21a38-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="21a38-122">W polu **Opis e-maila** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="21a38-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="21a38-123">W polu **Adres e-mail nadawcy** wprowadź adres e-mail nadawcy.</span><span class="sxs-lookup"><span data-stu-id="21a38-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="21a38-124">W sekcji **Ogólne** wprowadź wymagane informacje opcjonalne (takie jak priorytet wiadomości e-mail).</span><span class="sxs-lookup"><span data-stu-id="21a38-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="21a38-125">Rozwiń sekcję **Treść wiadomości E-mail** i wybierz opcję **Nowy**, aby utworzyć zawartość szablonu.</span><span class="sxs-lookup"><span data-stu-id="21a38-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="21a38-126">Dla każdego elementu zawartości wybierz język i podaj wiersz tematu wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="21a38-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="21a38-127">Jeśli wiadomość e-mail będzie zawierała treść, upewnij się, że pole **Zawiera treść** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="21a38-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="21a38-128">W okienku akcji wybierz **Wiadomość e-mail**, aby podać szablon treści wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="21a38-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="21a38-129">Na poniższym obrazie przedstawiono przykładowe ustawienia szablonów wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="21a38-129">The following image shows some example email template settings.</span></span>

![Ustawienia szablonu wiadomości e-mail](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="21a38-131">Tworzenie wydarzenia e-mail</span><span class="sxs-lookup"><span data-stu-id="21a38-131">Create an email event</span></span>

<span data-ttu-id="21a38-132">Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="21a38-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="21a38-133">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="21a38-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="21a38-134">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="21a38-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="21a38-135">Wybierz szablon wiadomości e-mail z listy rozwijanej **Identyfikator e-mail**.</span><span class="sxs-lookup"><span data-stu-id="21a38-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="21a38-136">Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="21a38-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="21a38-137">Zaznacz pole wyboru **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="21a38-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="21a38-138">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21a38-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="21a38-139">Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.</span><span class="sxs-lookup"><span data-stu-id="21a38-139">The following image shows some example event notification settings.</span></span>

![Ustawienia powiadomień wydarzeń](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="21a38-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="21a38-141">Additional resources</span></span>

[<span data-ttu-id="21a38-142">Konfigurowanie i wysyłanie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="21a38-142">Configure and send email</span></span>](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email)

[<span data-ttu-id="21a38-143">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="21a38-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="21a38-144">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="21a38-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="21a38-145">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="21a38-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
