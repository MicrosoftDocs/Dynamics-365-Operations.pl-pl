---
title: Konfigurowanie powiadomień pocztą e-mail
description: W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
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
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 17ffdcbf4b1801bd6ee9c9ddc18622d5d04b8a98
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3180202"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="025eb-103">Konfigurowanie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="025eb-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="025eb-104">W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="025eb-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="025eb-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="025eb-105">Overview</span></span>

<span data-ttu-id="025eb-106">Przed utworzeniem kanałów należy skonfigurować profil, aby zapewnić możliwość wysyłania powiadomień pocztą e-mail dla różnych zdarzeń, takich jak tworzenie zamówień, stan wysyłki zamówienia i niepowodzenia płatności.</span><span class="sxs-lookup"><span data-stu-id="025eb-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="025eb-107">Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="025eb-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="025eb-108">Tworzenie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="025eb-108">Create an email notification profile</span></span>

<span data-ttu-id="025eb-109">Aby utworzyć profil powiadomień e-mail, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="025eb-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="025eb-110">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="025eb-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="025eb-111">W okienku akcji kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="025eb-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="025eb-112">W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.</span><span class="sxs-lookup"><span data-stu-id="025eb-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="025eb-113">W polu **Opis** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="025eb-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="025eb-114">Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="025eb-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="025eb-115">Tworzenie szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="025eb-115">Create an email template</span></span>

<span data-ttu-id="025eb-116">Aby można było utworzyć powiadomienie e-mail, należy utworzyć szablon wiadomości e-mail organizacji zawierający informacje o adresach e-mail nadawców oraz szablon wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="025eb-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="025eb-117">Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="025eb-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="025eb-118">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Parametry sieci sprzedaży \> Szablony e-maili organizacji**.</span><span class="sxs-lookup"><span data-stu-id="025eb-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="025eb-119">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="025eb-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="025eb-120">W polu **Identyfikator e-mail** wprowadź identyfikator ułatwiający identyfikację tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="025eb-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="025eb-121">W polu **Nazwa wysyłającego** wprowadź nazwę wysyłającego.</span><span class="sxs-lookup"><span data-stu-id="025eb-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="025eb-122">W polu **Opis e-maila** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="025eb-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="025eb-123">W polu **Adres e-mail nadawcy** wprowadź adres e-mail nadawcy.</span><span class="sxs-lookup"><span data-stu-id="025eb-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="025eb-124">W sekcji **Ogólne** wprowadź wymagane informacje opcjonalne (takie jak priorytet wiadomości e-mail).</span><span class="sxs-lookup"><span data-stu-id="025eb-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="025eb-125">Rozwiń sekcję **Treść wiadomości E-mail** i wybierz opcję **Nowy**, aby utworzyć zawartość szablonu.</span><span class="sxs-lookup"><span data-stu-id="025eb-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="025eb-126">Dla każdego elementu zawartości wybierz język i podaj wiersz tematu wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="025eb-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="025eb-127">Jeśli wiadomość e-mail będzie zawierała treść, upewnij się, że pole **Zawiera treść** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="025eb-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="025eb-128">W okienku akcji wybierz **Wiadomość e-mail**, aby podać szablon treści wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="025eb-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="025eb-129">Na poniższym obrazie przedstawiono przykładowe ustawienia szablonów wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="025eb-129">The following image shows some example email template settings.</span></span>

![Ustawienia szablonu wiadomości e-mail](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="025eb-131">Tworzenie wydarzenia e-mail</span><span class="sxs-lookup"><span data-stu-id="025eb-131">Create an email event</span></span>

<span data-ttu-id="025eb-132">Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="025eb-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="025eb-133">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="025eb-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="025eb-134">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="025eb-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="025eb-135">Wybierz szablon wiadomości e-mail z listy rozwijanej **Identyfikator e-mail**.</span><span class="sxs-lookup"><span data-stu-id="025eb-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="025eb-136">Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="025eb-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="025eb-137">Zaznacz pole wyboru **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="025eb-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="025eb-138">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="025eb-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="025eb-139">Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.</span><span class="sxs-lookup"><span data-stu-id="025eb-139">The following image shows some example event notification settings.</span></span>

![Ustawienia powiadomień wydarzeń](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="025eb-141">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="025eb-141">Next steps</span></span>

<span data-ttu-id="025eb-142">Aby można było wysyłać wiadomości, należy skonfigurować usługę poczty wychodzącej i skonfigurować zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="025eb-142">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="025eb-143">Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="025eb-143">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="025eb-144">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="025eb-144">Additional resources</span></span>

[<span data-ttu-id="025eb-145">Konfigurowanie i wysyłanie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="025eb-145">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="025eb-146">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="025eb-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="025eb-147">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="025eb-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="025eb-148">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="025eb-148">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
