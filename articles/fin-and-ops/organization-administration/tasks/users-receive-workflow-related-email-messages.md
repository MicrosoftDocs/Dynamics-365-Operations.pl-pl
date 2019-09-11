---
title: Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy
description: Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916399"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="cfa1c-103">Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy</span><span class="sxs-lookup"><span data-stu-id="cfa1c-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cfa1c-104">Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="cfa1c-105">Na przykład, wiadomości e-mail mogą być wysyłane do użytkowników po przypisaniu do nich dokumentów do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="cfa1c-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="cfa1c-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="cfa1c-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cfa1c-109">W **Okienku akcji** kliknij **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="cfa1c-110">Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja **Powiadomienia** została rozwinięta.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="cfa1c-111">W sekcji **Powiadomienia** można określić sposób, w jaki użytkownik ma zostać powiadomiony o zdarzeniach związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="cfa1c-112">W polu **Typ powiadomienia przepływu pracy dla pozycji w wierszu** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="cfa1c-113">Zgrupowane — Powiadomienia dla towarów w wierszach są grupowane w jedną wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="cfa1c-114">Indywidualne — Wiadomość e-mail zostanie wysłana dla każdego towaru w wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="cfa1c-115">Jeśli chcesz, aby użytkownik otrzymywał powiadomienia w kliencie, zaznacz pole wyboru **Wysyłaj powiadomienia pocztą e-mail**.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="cfa1c-116">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-116">Click **Save**.</span></span>
7. <span data-ttu-id="cfa1c-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfa1c-117">Close the page.</span></span>

