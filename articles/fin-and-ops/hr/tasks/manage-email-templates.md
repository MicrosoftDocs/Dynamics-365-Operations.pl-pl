--- 
title: "Zarządzanie szablonami wiadomości e-mail"
description: "Można przenieść informacje z bazy danych organizacji do zakładek w nowym dokumencie i używać ich w szablonach, które pomagają efektywnie komunikować się z kandydatami."
author: ShielaSogge
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: dbe665688d9fb10ce200f25b6552f49349cfc42e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="manage-email-templates"></a><span data-ttu-id="3bc9b-103">Zarządzanie szablonami wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="3bc9b-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3bc9b-104">Można przenieść informacje z bazy danych organizacji do zakładek w nowym dokumencie i używać ich w szablonach, które pomagają efektywnie komunikować się z kandydatami.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="3bc9b-105">W tym celu należy utworzyć szablon, który zawiera standardowy tekst i kilka zakładek, gdzie należy wstawić dane systemowe.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="3bc9b-106">Na przykład można wstawić informacje adresowe i kontaktowe kandydata do dokumentu programu Microsoft Word, który będzie używany podczas komunikowania się z danym kandydatem.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="3bc9b-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="3bc9b-108">Wybieranie zakładek do używania w szablonach wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="3bc9b-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="3bc9b-109">Kliknij opcję Zakładki zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="3bc9b-110">Na liście znajdź i zaznacz odpowiednią akcję korespondencyjną.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="3bc9b-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-111">Click Edit.</span></span>
4. <span data-ttu-id="3bc9b-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3bc9b-113">Wybierz pola, których chcesz móc używać w szablonie wiadomości e-mail dla wybranej akcji korespondencyjnej, i przenieś je do pól zakładek.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="3bc9b-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="3bc9b-115">Tworzenie szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="3bc9b-115">Create an email template</span></span>
1. <span data-ttu-id="3bc9b-116">Wybierz kolejno opcje Zasoby ludzkie > Rekrutacja > Komunikacja > Szablony wiadomości e-mail dotyczące zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="3bc9b-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-117">Click New.</span></span>
3. <span data-ttu-id="3bc9b-118">W polu Akcja korespondencyjna wybierz opcję „Rozmowa kwalifikacyjna”.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="3bc9b-119">Wybierz akcję korespondencyjną, którą zawiera zakładki przeznaczone do używania w tego typu komunikacji pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="3bc9b-120">W polu Szablon wiadomości e-mail wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="3bc9b-121">W polu Temat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="3bc9b-122">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="3bc9b-123">Na liście znajdź i zaznacz odpowiednie pole zakładki.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="3bc9b-124">Kontynuuj wpisywanie swojej wiadomości e-mail, w razie potrzeby wstawiając pola zakładek.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="3bc9b-125">Kontynuuj wpisywanie swojej wiadomości e-mail, w razie potrzeby wstawiając pola zakładek.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="3bc9b-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3bc9b-126">Click Save.</span></span>


