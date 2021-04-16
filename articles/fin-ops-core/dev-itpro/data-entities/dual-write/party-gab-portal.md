---
title: Korzystanie z usługi Power Portal z modelem danych strony
description: W tym temacie opisano zmiany ról sieci web usługi Power Portal z powodu modelu danych stron w trybie podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833097"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="5a4d8-103">Korzystanie z usługi Power Portal z modelem danych strony</span><span class="sxs-lookup"><span data-stu-id="5a4d8-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5a4d8-104">Wersja rozwiązania Dual-write Application Orchestration 2.0.999.0 a następnie zawiera zmiany modelu danych w tabelach Party i globalna książka adresowa Danych i Kontakt.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="5a4d8-105">Zmiany umożliwiają obsługę relacji typu „wiele do wielu”, które obsługują zaawansowane scenariusze biznesowe.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="5a4d8-106">Te zmiany nie są obsługiwane przez role sieci web portalu, w tym portal dla klientów, które są wysyłane poza polem lub istniały w środowisku przed zainstalowaniem podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="5a4d8-107">Aby role sieci web działały zgodnie z oczekiwaniami, trzeba utworzyć nowe role sieci web przy użyciu nowego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="5a4d8-108">Podsumowując, sposób interakcji tabel uległ zmianie, ale uprawnienia tabel w portalu klientów nie zostały zmienione.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="5a4d8-109">W tym temacie opisano sposób tworzenia nowych ról sieci web, które działają z nowym zaawansowanym modelem danych.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="5a4d8-110">Ten schemat przedstawia relację tabeli **bez** strony globalna książka adresowa modelu danych:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![bez modelu strony](media/without-party-model.PNG)

<span data-ttu-id="5a4d8-112">Ten schemat przedstawia relację tabeli **ze** stroną globalnej książki adresowej modelu danych:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![z modelem strony](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="5a4d8-114">Utwórz nowe uprawnienie do tabeli</span><span class="sxs-lookup"><span data-stu-id="5a4d8-114">Create a new table permission</span></span>

<span data-ttu-id="5a4d8-115">Aby utworzyć nowe uprawnienia tabeli, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="5a4d8-116">Zaloguj się do [Power Apps](https://make.powerapps.com) i przejdź do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="5a4d8-117">Wybierz aplikację Zarządzanie portalem.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="5a4d8-118">Na pasku bocznym wybierz pozycję **Zabezpieczenia > Uprawnienia tabeli**.</span><span class="sxs-lookup"><span data-stu-id="5a4d8-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="5a4d8-119">Należy utworzyć trzy nowe uprawnienia:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="5a4d8-120">Połączenie osoba kontaktowa ze stroną</span><span class="sxs-lookup"><span data-stu-id="5a4d8-120">Contact to Party connection</span></span>
    + <span data-ttu-id="5a4d8-121">Strona połączonego konta</span><span class="sxs-lookup"><span data-stu-id="5a4d8-121">Party to Account connection</span></span>
    + <span data-ttu-id="5a4d8-122">Konto połączonego zamówienia</span><span class="sxs-lookup"><span data-stu-id="5a4d8-122">Account to Order connection</span></span>

4. <span data-ttu-id="5a4d8-123">Utwórz i zapisz nowe uprawnienie dla kontaktu do połączenia ze stroną, ustawiając następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="5a4d8-124">**Nazwa:** stroną połączonego konta (lub do wyboru)</span><span class="sxs-lookup"><span data-stu-id="5a4d8-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="5a4d8-125">**Nazwa tabeli**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="5a4d8-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="5a4d8-126">**Witryna**: Portal klienta</span><span class="sxs-lookup"><span data-stu-id="5a4d8-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="5a4d8-127">**Zakres:** Osoba kontaktowa</span><span class="sxs-lookup"><span data-stu-id="5a4d8-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="5a4d8-128">**Uprawnienia**: zaznacz wszystkie</span><span class="sxs-lookup"><span data-stu-id="5a4d8-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="5a4d8-129">**Role sieci Web:** uwierzytelnieni użytkownicy, przedstawiciel odbiorcy (lub wybór użytkownika)</span><span class="sxs-lookup"><span data-stu-id="5a4d8-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="5a4d8-130">Utwórz i zapisz nowe uprawnienie dla kontaktu do połączenia ze stroną, ustawiając następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="5a4d8-131">**Nazwa:** stroną połączonego konta (lub do wyboru)</span><span class="sxs-lookup"><span data-stu-id="5a4d8-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="5a4d8-132">**Nazwa tabeli**: konto</span><span class="sxs-lookup"><span data-stu-id="5a4d8-132">**Table Name**: account</span></span>
    + <span data-ttu-id="5a4d8-133">**Witryna**: Portal klienta</span><span class="sxs-lookup"><span data-stu-id="5a4d8-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="5a4d8-134">**Zakres**: nadrzędny</span><span class="sxs-lookup"><span data-stu-id="5a4d8-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="5a4d8-135">**Uprawnienia**: zaznacz wszystkie</span><span class="sxs-lookup"><span data-stu-id="5a4d8-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="5a4d8-136">**Uprawnienie tabeli nadrzędnej**: połączenie ze stroną</span><span class="sxs-lookup"><span data-stu-id="5a4d8-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="5a4d8-137">Utwórz i zapisz nowe uprawnienie dla konta do połączenia z zamówieniem, ustawiając następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="5a4d8-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="5a4d8-138">**Nazwa:** konto do połączenia z zamówieniem (lub do wyboru)</span><span class="sxs-lookup"><span data-stu-id="5a4d8-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="5a4d8-139">**Nazwa tabeli**: zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="5a4d8-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="5a4d8-140">**Witryna**: Portal klienta</span><span class="sxs-lookup"><span data-stu-id="5a4d8-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="5a4d8-141">**Zakres**: nadrzędny</span><span class="sxs-lookup"><span data-stu-id="5a4d8-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="5a4d8-142">**Uprawnienia**: zaznacz wszystkie</span><span class="sxs-lookup"><span data-stu-id="5a4d8-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="5a4d8-143">**Uprawnienie tabeli nadrzędnej**: połączenie strona do konta</span><span class="sxs-lookup"><span data-stu-id="5a4d8-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
