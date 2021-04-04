---
title: Konfigurowanie powiadomień pocztą e-mail
description: W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555314"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="ed4b0-103">Konfigurowanie profilu powiadomienia</span><span class="sxs-lookup"><span data-stu-id="ed4b0-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ed4b0-104">W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ed4b0-105">Podczas tworzenia kanałów można skonfigurować profil powiadomienia pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="ed4b0-106">W ten sposób wiadomości e-mail mogą być wysyłane do odbiorców w związku z różnymi zdarzeniami transakcyjnmi, takimi jak tworzenie zamówienia, stan wysyłki zamówienia czy niepowodzenie płatności.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="ed4b0-107">Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="ed4b0-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="ed4b0-108">Tworzenie powiadomień pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="ed4b0-108">Create an email notification profile</span></span>

<span data-ttu-id="ed4b0-109">Aby utworzyć profil powiadomień e-mail, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="ed4b0-110">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="ed4b0-111">W okienku akcji kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="ed4b0-112">W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="ed4b0-113">W polu **Opis** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="ed4b0-114">Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="ed4b0-115">Tworzenie szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="ed4b0-115">Create an email template</span></span>

<span data-ttu-id="ed4b0-116">Aby można było włączyć typ powiadomienia pocztą e-mail, należy utworzyć szablon wiadomości e-mail organizacji w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="ed4b0-117">Ten szablon definiuje temat wiadomości e-mail, nadawcę, domyślny język i treść wiadomości e-mail dla każdego języka, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="ed4b0-118">Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="ed4b0-119">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Parametry sieci sprzedaży \> Szablony e-maili organizacji**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="ed4b0-120">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ed4b0-121">W polu **Identyfikator e-mail** wprowadź identyfikator ułatwiający identyfikację tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="ed4b0-122">W polu **Nazwa wysyłającego** wprowadź nazwę wysyłającego.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="ed4b0-123">W polu **Opis e-maila** wprowadź odpowiedni opis.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="ed4b0-124">W polu **Adres e-mail nadawcy** wprowadź adres e-mail nadawcy.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="ed4b0-125">W sekcji **Ogólne** wybierz domyślny język szablonu wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="ed4b0-126">Domyślny język będzie używany, gdy dla określonego języka nie istnieje żaden zlokalizowany szablon.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="ed4b0-127">Rozwiń sekcję **Treść wiadomości E-mail** i wybierz opcję **Nowy**, aby utworzyć zawartość szablonu.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="ed4b0-128">Dla każdego elementu zawartości wybierz język i podaj wiersz tematu wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="ed4b0-129">Jeśli wiadomość e-mail będzie zawierała treść, upewnij się, że pole **Zawiera treść** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="ed4b0-130">W okienku akcji wybierz **Wiadomość e-mail**, aby podać szablon treści wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="ed4b0-131">Na poniższym obrazie przedstawiono przykładowe ustawienia szablonów wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-131">The following image shows some example email template settings.</span></span>

![Ustawienia szablonu wiadomości e-mail](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="ed4b0-133">Tworzenie wydarzenia e-mail</span><span class="sxs-lookup"><span data-stu-id="ed4b0-133">Create an email event</span></span>

<span data-ttu-id="ed4b0-134">Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="ed4b0-135">W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="ed4b0-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="ed4b0-137">Wybierz szablon wiadomości e-mail z listy rozwijanej **Identyfikator e-mail**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="ed4b0-138">Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="ed4b0-139">Zaznacz pole wyboru **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="ed4b0-140">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ed4b0-141">Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-141">The following image shows some example event notification settings.</span></span>

![Ustawienia powiadomień wydarzeń](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="ed4b0-143">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ed4b0-143">Next steps</span></span>

<span data-ttu-id="ed4b0-144">Aby można było wysyłać wiadomości, należy skonfigurować usługę poczty wychodzącej i skonfigurować zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="ed4b0-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="ed4b0-145">Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="ed4b0-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="ed4b0-146">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ed4b0-146">Additional resources</span></span>

[<span data-ttu-id="ed4b0-147">Konfigurowanie i wysyłanie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="ed4b0-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ed4b0-148">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="ed4b0-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ed4b0-149">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="ed4b0-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="ed4b0-150">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="ed4b0-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
