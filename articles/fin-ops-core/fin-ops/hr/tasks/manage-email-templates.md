---
title: Zarządzanie szablonami wiadomości e-mail
description: W tym temacie wyjaśniono sposób można zarządzać szablonami wiadomości e-mail.
author: andreabichsel
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41777436a624f9b98956553243056b92a00c1ed6
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693877"
---
# <a name="manage-email-templates"></a><span data-ttu-id="c7efa-103">Zarządzanie szablonami wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="c7efa-103">Manage email templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7efa-104">Można przenieść informacje z bazy danych organizacji do zakładek w nowym dokumencie i używać ich w szablonach, które pomagają efektywnie komunikować się z kandydatami.</span><span class="sxs-lookup"><span data-stu-id="c7efa-104">You can transfer information from your organization's database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="c7efa-105">W tym celu należy utworzyć szablon, który zawiera standardowy tekst i kilka zakładek, gdzie należy wstawić dane systemowe.</span><span class="sxs-lookup"><span data-stu-id="c7efa-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="c7efa-106">Na przykład można wstawić informacje adresowe i kontaktowe kandydata do dokumentu programu Microsoft Word, który będzie używany podczas komunikowania się z danym kandydatem.</span><span class="sxs-lookup"><span data-stu-id="c7efa-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="c7efa-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c7efa-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="c7efa-108">Wybieranie zakładek do używania w szablonach wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="c7efa-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="c7efa-109">W okienku nawigacji przejdź do **Moduły > Zasoby ludzkie > Rekrutacja > Komunikacja > Zakładki zgłoszeń**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-109">In the navigation pane, go to **Modules > Human Resources > Recruitment > Communication > Application bookmarks**.</span></span>
2. <span data-ttu-id="c7efa-110">Na liście znajdź i zaznacz odpowiednią akcję korespondencyjną.</span><span class="sxs-lookup"><span data-stu-id="c7efa-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="c7efa-111">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-111">Select **Edit**.</span></span>
4. <span data-ttu-id="c7efa-112">Wybierz pola, których chcesz móc używać w szablonie wiadomości e-mail dla wybranej akcji korespondencyjnej, i przenieś je do pól zakładek.</span><span class="sxs-lookup"><span data-stu-id="c7efa-112">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="c7efa-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c7efa-113">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="c7efa-114">Tworzenie szablonu wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="c7efa-114">Create an email template</span></span>
1. <span data-ttu-id="c7efa-115">W okienku nawigacji przejdź do **Moduły > Zasoby ludzkie > Rekrutacja > Komunikacja > Szablony wiadomości e-mail dotyczące zgłoszeń**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-115">In the navigation pane, go to **Modules > Human resources > Recruitment > Communication > Application e-mail templates**.</span></span>
2. <span data-ttu-id="c7efa-116">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-116">Select **New**.</span></span>
3. <span data-ttu-id="c7efa-117">W polu **Akcja korespondencyjna** wybierz opcję **Rozmowa kwalifikacyjna**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-117">In the **Correspondence action** field, select **Interview**.</span></span> <span data-ttu-id="c7efa-118">Wybierz akcję korespondencyjną, którą zawiera zakładki przeznaczone do używania w tego typu komunikacji pocztą e-mail.</span><span class="sxs-lookup"><span data-stu-id="c7efa-118">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="c7efa-119">W polu **Szablon wiadomości e-mail** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c7efa-119">In the **E-mail template** field, type a value.</span></span>
5. <span data-ttu-id="c7efa-120">W polu **Temat** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c7efa-120">In the **Subject** field, type a value.</span></span>
6. <span data-ttu-id="c7efa-121">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c7efa-121">In the **Text** field, type a value.</span></span>
7. <span data-ttu-id="c7efa-122">Na liście znajdź i zaznacz odpowiednie pole zakładki.</span><span class="sxs-lookup"><span data-stu-id="c7efa-122">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="c7efa-123">Kontynuuj wpisywanie swojej wiadomości e-mail, w razie potrzeby wstawiając pola zakładek.</span><span class="sxs-lookup"><span data-stu-id="c7efa-123">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
9. <span data-ttu-id="c7efa-124">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c7efa-124">Select **Save**.</span></span>

