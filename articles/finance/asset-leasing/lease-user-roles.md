---
title: Przypisywanie ról użytkownikom w wynajmie
description: W tym temacie opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku. Opisano tu również sposób przypisywania użytkowników do tych ról.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 09d80e9629b60144665441989d9d63d7f6be3c60
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207286"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="affa4-104">Przypisywanie ról użytkownikom w wynajmie</span><span class="sxs-lookup"><span data-stu-id="affa4-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="affa4-105">W tym temacie opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="affa4-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="affa4-106">Opisano tu również sposób przypisywania użytkowników do tych ról.</span><span class="sxs-lookup"><span data-stu-id="affa4-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="affa4-107">Trzy role użytkowników różnicują dostęp w module Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="affa4-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="affa4-108">Jedna rola jest odpowiednia do obsługi umów wynajmu, jedna jest odpowiednia do przeglądania umów wynajmu, a jedna jest odpowiednia do wykonywania obowiązków pracownika wykonującego umowy leasingu.</span><span class="sxs-lookup"><span data-stu-id="affa4-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="affa4-109">Każda rola ma określone uprawnienia dla wszystkich stron dokumentu umowy leasingu oraz pozwala użytkownikom wyświetlać, tworzyć, edytować i usuwać umowy wynajmu, zgodnie z ich służbowymi obowiązkami.</span><span class="sxs-lookup"><span data-stu-id="affa4-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="affa4-110">Rola</span><span class="sxs-lookup"><span data-stu-id="affa4-110">Role</span></span>           | <span data-ttu-id="affa4-111">opis</span><span class="sxs-lookup"><span data-stu-id="affa4-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="affa4-112">Obsługa wynajmu</span><span class="sxs-lookup"><span data-stu-id="affa4-112">Maintain Lease</span></span> | <span data-ttu-id="affa4-113">Użytkownicy w tej roli mogą dodawać, edytować, usuwać i wyświetlać umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="affa4-114">Ta rola jest przeznaczona dla użytkowników, których codzienne zadania obejmują tworzenie i księgowanie miesięcznych wpisów w arkuszach oraz dodawanie nowych umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="affa4-115">Ta rola daje dostęp do wszystkich funkcji modułu Obsługa wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="affa4-116">Wyświetl wynajem</span><span class="sxs-lookup"><span data-stu-id="affa4-116">View Lease</span></span>     | <span data-ttu-id="affa4-117">Użytkownicy w tej roli mogą tylko wyświetlać rekordy umowy wynajmu i harmonogramy oraz generować raporty.</span><span class="sxs-lookup"><span data-stu-id="affa4-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="affa4-118">Nie mogą tworzyć nowych umów wynajmu, edytować istniejących umów wynajmu ani tworzyć wpisów w arkuszach dla umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="affa4-119">Ta rola jest przeznaczona dla użytkowników, którzy potrzebują tylko wglądu w umowy wynajmu, harmonogramy i transakcje dotyczące tych umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="affa4-120">Pracownik wynajmu</span><span class="sxs-lookup"><span data-stu-id="affa4-120">Lease Clerk</span></span>    | <span data-ttu-id="affa4-121">Użytkownicy w tej roli mogą tylko tworzyć nowe umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="affa4-122">Nie mogą edytować ani usuwać istniejących umów wynajmu, wyświetlać harmonogramów umów wynajmu ani księgować wpisów w arkuszu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="affa4-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="affa4-123">Ta rola jest przeznaczona dla użytkowników zajmujących się wprowadzaniem danych.</span><span class="sxs-lookup"><span data-stu-id="affa4-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="affa4-124">Aby przypisać użytkowników do ról używanych w module Wynajem składnika majątku, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="affa4-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="affa4-125">Wybierz kolejno opcje **Administrowanie systemem \> Zabezpieczenia \> Przypisywanie użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="affa4-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="affa4-126">Wybierz rolę **Obsługa wynajmu**, **Pracownik wynajmu** lub **Wyświetl wynajem**, a następnie wybierz opcję **Ręcznie przypisz/wyklucz użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="affa4-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="affa4-127">Wybierz użytkownika, który ma zostać przypisany do roli, a następnie wybierz opcję **Przypisz do roli**.</span><span class="sxs-lookup"><span data-stu-id="affa4-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]