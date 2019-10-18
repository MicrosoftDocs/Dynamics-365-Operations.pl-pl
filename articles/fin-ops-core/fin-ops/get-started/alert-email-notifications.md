---
title: Powiadomienia o alertach klienta wysyłane pocztą e-mail
description: Ten temat zawiera informacje dotyczące sposobu konfigurowania reguł wysyłania pocztą e-mail powiadomień o wystąpieniu zdefiniowanych zdarzeń.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: ba92c3dc1debed7e98210168d1a135e2cf567aec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191300"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="95141-103">Powiadomienia o alertach klienta wysyłane pocztą e-mail</span><span class="sxs-lookup"><span data-stu-id="95141-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="95141-104">Można zdefiniować niestandardowe reguły alertów umożliwiające monitorowanie filtrowanych widoków danych i automatyczne wysyłanie powiadomień pocztą e-mail po wystąpieniu zdarzeń wstępnie zdefiniowanych.</span><span class="sxs-lookup"><span data-stu-id="95141-104">You can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="95141-105">Opcja wysyłania powiadomień pocztą e-mail jest dostępna dla wszystkich obsługiwanych typów alertów i można już również włączyć dla istniejących reguł alertów.</span><span class="sxs-lookup"><span data-stu-id="95141-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="95141-106">Można używać wbudowanych formantów do tworzenia reguł alertów monitorujących przefiltrowane widoki zadań wsadowych systemu.</span><span class="sxs-lookup"><span data-stu-id="95141-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="95141-107">Monitorowanie wartości pola **Stan** pozwala również skonfigurować reguły alertów, które wysyłają wiadomość e-mail, kiedy zadanie wsadowe nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="95141-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="95141-108">Po utworzeniu tych reguł alertów nie trzeba już sprawdzać raportów dotyczących zmian danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="95141-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="95141-109">Zamiast tego można zlecić monitorowanie usłudze inteligentnego wykrywania zmian.</span><span class="sxs-lookup"><span data-stu-id="95141-109">Instead, you can let the intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="95141-110">Alerty klienta zależą od podsystemu e-mail dostarczonego za pośrednictwem integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="95141-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="95141-111">Zaleca się korzystanie z usług dostawcy protokołu SMTP (Simple Mail Transfer Protocol), dzięki czemu dystrybucja wiadomości e-mail nie musi opierać się na lokalnym kliencie poczty.</span><span class="sxs-lookup"><span data-stu-id="95141-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="95141-112">Aby wysłać powiadomienia pocztą e-mail, należy skonfigurować usługi zintegrowanych wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="95141-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="95141-113">Powiadomienia e-mail są wysyłane do adresatów w imieniu właścicieli alertów.</span><span class="sxs-lookup"><span data-stu-id="95141-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="95141-114">Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="95141-114">For more information about how to configure email, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="95141-115">Poniższy obraz przedstawia okno dialogowe **Utwórz regułę alertu**, które teraz zawiera opcję **Wyślij wiadomość e-mail**.</span><span class="sxs-lookup"><span data-stu-id="95141-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="95141-116">[![Okno dialogowe Utwórz regułę alertu z opcją Wyślij wiadomość e-mail ustawioną na wartość Tak](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="95141-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="95141-117">Gdy opcja **Wyślij wiadomość e-mail** ma wartość **Tak**, powiadomienia o alertach będą nadal dostarczane z Centrum akcji.</span><span class="sxs-lookup"><span data-stu-id="95141-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="95141-118">Szablony wiadomości e-mail z powiadomieniem o alercie</span><span class="sxs-lookup"><span data-stu-id="95141-118">Alert notification email templates</span></span>

<span data-ttu-id="95141-119">Usługa wysyła powiadomienia e-mail przy użyciu wstępnie zdefiniowanych szablonów wiadomości e-mail zawierających podstawowe informacje powiadomienia o alercie.</span><span class="sxs-lookup"><span data-stu-id="95141-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="95141-120">Poniższa ilustracja pokazuje strukturę powiadomień o alertach po ich odebraniu pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="95141-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="95141-121">[![Powiadomienia o alertach oparte na szablonach i służące do rejestrowania tworzenia, zmian pól i wykrywania szablonów](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="95141-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
