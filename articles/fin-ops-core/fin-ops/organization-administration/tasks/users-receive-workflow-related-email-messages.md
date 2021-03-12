---
title: Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy
description: Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799011"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="e65f9-103">Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy</span><span class="sxs-lookup"><span data-stu-id="e65f9-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e65f9-104">Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="e65f9-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="e65f9-105">Na przykład, wiadomości e-mail mogą być wysyłane do użytkowników po przypisaniu do nich dokumentów do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="e65f9-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="e65f9-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e65f9-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="e65f9-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="e65f9-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="e65f9-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e65f9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e65f9-109">W **Okienku akcji** kliknij **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="e65f9-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="e65f9-110">Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja **Powiadomienia** została rozwinięta.</span><span class="sxs-lookup"><span data-stu-id="e65f9-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="e65f9-111">W sekcji **Powiadomienia** można określić sposób, w jaki użytkownik ma zostać powiadomiony o zdarzeniach związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="e65f9-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="e65f9-112">W polu **Typ powiadomienia przepływu pracy dla pozycji w wierszu** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="e65f9-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="e65f9-113">Zgrupowane — Powiadomienia dla towarów w wierszach są grupowane w jedną wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="e65f9-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="e65f9-114">Indywidualne — Wiadomość e-mail zostanie wysłana dla każdego towaru w wierszu.</span><span class="sxs-lookup"><span data-stu-id="e65f9-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="e65f9-115">Jeśli chcesz, aby użytkownik otrzymywał powiadomienia w kliencie, zaznacz pole wyboru **Wysyłaj powiadomienia pocztą e-mail**.</span><span class="sxs-lookup"><span data-stu-id="e65f9-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="e65f9-116">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e65f9-116">Click **Save**.</span></span>
7. <span data-ttu-id="e65f9-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e65f9-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="e65f9-118">Szablony wiadomości e-mail przepływu pracy będą czerpane z szablonów wiadomości e-mail systemu lub szablonów wiadomości e-mail organizacji w zależności od tego, czy przepływ pracy jest przepływem pracy na poziomie systemu (nie dotyczący firmy), czy na poziomie organizacji (dotyczący firmy).</span><span class="sxs-lookup"><span data-stu-id="e65f9-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>
