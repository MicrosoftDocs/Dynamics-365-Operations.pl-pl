--- 
title: "Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy"
description: "Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy."
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: abd59b96a2e5dceb2492c2db2c617485b332fbd3
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.contentlocale: pl-pl
ms.lasthandoff: 09/13/2018

---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="6b6a6-103">Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy</span><span class="sxs-lookup"><span data-stu-id="6b6a6-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6b6a6-104">Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="6b6a6-105">Na przykład, wiadomości e-mail mogą być wysyłane do użytkowników po przypisaniu do nich dokumentów do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="6b6a6-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="6b6a6-107">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="6b6a6-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6b6a6-109">Kliknij opcję Opcje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-109">Click User options.</span></span>
4. <span data-ttu-id="6b6a6-110">Kliknij kartę Przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="6b6a6-111">Upewnij się, że jest rozwinięta sekcja Powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="6b6a6-112">W sekcji Powiadomienia można określić sposób, w jaki użytkownik ma zostać powiadomiony o zdarzeniach związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="6b6a6-113">W polu Typ powiadomienia przepływu pracy dla pozycji w wierszu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="6b6a6-114">Zgrupowane — Powiadomienia dla towarów w wierszach są grupowane w jedną wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="6b6a6-115">Indywidualne — Wiadomość e-mail zostanie wysłana dla każdego towaru w wierszu.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="6b6a6-116">Jeśli chcesz, aby użytkownik otrzymywał powiadomienia na kliencie, zaznacz pole wyboru Wysyłaj powiadomienia pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="6b6a6-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-117">Click Save.</span></span>
7. <span data-ttu-id="6b6a6-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6b6a6-118">Close the page.</span></span>


