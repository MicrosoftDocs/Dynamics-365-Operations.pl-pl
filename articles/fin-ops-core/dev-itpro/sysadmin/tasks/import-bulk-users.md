---
title: Importowanie użytkowników z usługi Azure Active Directory
description: Ta procedura umożliwia administratorom systemów ręczne importowanie wybranych użytkowników lub importowanie dużej liczby użytkowników z usługi Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679821"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="73249-103">Importowanie użytkowników z usługi Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="73249-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="73249-104">Importowanie wybranych użytkowników</span><span class="sxs-lookup"><span data-stu-id="73249-104">Import select users</span></span>

<span data-ttu-id="73249-105">Ta procedura umożliwia administratorom systemów importowanie wybranych użytkowników z usługi Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="73249-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="73249-106">Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną.</span><span class="sxs-lookup"><span data-stu-id="73249-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="73249-107">W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.</span><span class="sxs-lookup"><span data-stu-id="73249-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="73249-108">Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="73249-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="73249-109">Kliknij opcję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="73249-109">Click **Import users**.</span></span>
4. <span data-ttu-id="73249-110">Zaznacz użytkowników, którzy mają zostać zaimportowani, i wybierz opcję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="73249-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="73249-111">Po zakończeniu importu trzeba będzie przypisać role użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="73249-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="73249-112">Zbiorowe importowanie użytkowników</span><span class="sxs-lookup"><span data-stu-id="73249-112">Import users in bulk</span></span>

<span data-ttu-id="73249-113">Ta procedura umożliwia administratorom systemów importowanie dużej liczby użytkowników z usługi Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="73249-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="73249-114">Zauważ, że w przypadku korzystania z opcji importu wsadowego nie można wybierać użytkowników.</span><span class="sxs-lookup"><span data-stu-id="73249-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="73249-115">Wykonywanie importu jako zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="73249-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="73249-116">Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną.</span><span class="sxs-lookup"><span data-stu-id="73249-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="73249-117">W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.</span><span class="sxs-lookup"><span data-stu-id="73249-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="73249-118">Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="73249-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="73249-119">Kliknij opcję **Import wsadowy**.</span><span class="sxs-lookup"><span data-stu-id="73249-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="73249-120">Rozwiń sekcję **Uruchom w tle**.</span><span class="sxs-lookup"><span data-stu-id="73249-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="73249-121">W polu **Przetwarzanie wsadowe** zaznacz opcję \*\*Tak.</span><span class="sxs-lookup"><span data-stu-id="73249-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="73249-122">W polu **Grupa zadań wsadowych** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="73249-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="73249-123">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="73249-123">This is an optional step.</span></span>  
7. <span data-ttu-id="73249-124">W polu **Prywatne** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="73249-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="73249-125">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="73249-125">This is an optional step.</span></span>  
8. <span data-ttu-id="73249-126">W polu **Zadanie o znaczeniu krytycznym** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="73249-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="73249-127">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="73249-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="73249-128">W polu \*\*Monitorowanie kategorii wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="73249-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="73249-129">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="73249-129">Click **OK**.</span></span>

<span data-ttu-id="73249-130">Po zakończeniu importu trzeba będzie przypisać role użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="73249-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="73249-131">Uruchamianie w środowisku piaskownicy</span><span class="sxs-lookup"><span data-stu-id="73249-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="73249-132">Wybierz opcję **Import wsadowy**.</span><span class="sxs-lookup"><span data-stu-id="73249-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="73249-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="73249-133">Select **OK**.</span></span>
