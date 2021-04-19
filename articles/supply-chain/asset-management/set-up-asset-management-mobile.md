---
title: Konfigurowanie mobilnego obszaru roboczego zarządzania składnikami majątku
description: W tym temacie opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Supply Chain Management i aplikacji mobilnej Finance and Operations (Dynamics 365) w celu uruchomienia mobilnego obszaru roboczego Zarządzanie składnikami majątku, za pomocą których pracownicy mogą wykonywać zadania zarządzania składnikami majątku.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: bc170df2fc58ae6b42fbc8834caad0bb7cd16f69
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837784"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="57acb-103">Konfigurowanie mobilnego obszaru roboczego zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="57acb-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57acb-104">W tym temacie opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Supply Chain Management i aplikacji mobilnej Finance and Operations (Dynamics 365) w celu uruchomienia mobilnego obszaru roboczego **Zarządzanie składnikami majątku**, za pomocą których pracownicy mogą wykonywać zadania zarządzania składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="57acb-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="57acb-105">Konfigurowanie użytkowników konserwatorów w aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="57acb-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="57acb-106">Dla każdego użytkownika, który wymaga dostępu do mobilnego obszaru roboczego **Zarządzanie składnikami majątku**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="57acb-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="57acb-107">W aplikacji Supply Chain Management przejdź do grupy **Zasoby ludzkie \> Pracownicy** i upewnij się, że dla użytkownika, który ma zostać ustawiony, istnieje rekord pracownika.</span><span class="sxs-lookup"><span data-stu-id="57acb-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="57acb-108">Utwórz nowy rekord pracownika zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="57acb-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="57acb-109">Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Pracownicy \> Pracownicy** i upewnij się, że rekord pracownika, który został zidentyfikowany (lub utworzony) w poprzednim kroku, jest zamapowany na rekord konserwatora.</span><span class="sxs-lookup"><span data-stu-id="57acb-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="57acb-110">Utwórz w razie potrzeby nowy rekord konserwatora i ustaw w polu **Pracownik** rekord pracownika z poprzedniego kroku.</span><span class="sxs-lookup"><span data-stu-id="57acb-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="57acb-111">Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Pracownicy \> Grupy konserwatorów** i upewnij się, że rekord konserwatora, który został zidentyfikowany (lub utworzony) w poprzednim kroku, należy do grupy konserwatorów.</span><span class="sxs-lookup"><span data-stu-id="57acb-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="57acb-112">Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="57acb-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="57acb-113">Wybierz odpowiedniego użytkownika w siatce.</span><span class="sxs-lookup"><span data-stu-id="57acb-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="57acb-114">Na skróconej karcie **Szczegóły użytkownika** ustaw pole **Osoba** na konto pracownika, które chcesz skojarzyć z bieżącym kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="57acb-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="57acb-115">To konto pracownika powinno być rekordem pracownika, który został zidentyfikowany (lub utworzony) w kroku 1 i zamapowany na rekord konserwatora w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="57acb-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="57acb-116">Uprawnienia użytkowników i role zabezpieczeń mają zastosowanie do funkcji mobilnego obszaru roboczego **Zarządzanie składnikami majątku** w ten sam sposób, jak do funkcji interfejsu użytkownika aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="57acb-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="57acb-117">Każdy użytkownik ustawiony do uzyskiwania dostępu do mobilnego obszaru roboczego **Zarządzanie składnikami majątku** musi mieć role zabezpieczeń wymagane do wykonywania podobnych operacji bezpośrednio w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="57acb-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="57acb-118">Publikowanie w mobilnym obszarze roboczym zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="57acb-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="57acb-119">Aby udostępnić funkcje zarządzania składnikami majątku w aplikacji mobilnej Finance and Operations (Dynamics 365), musisz opublikować mobilny obszar roboczy **Zarządzanie składnikami majątku**.</span><span class="sxs-lookup"><span data-stu-id="57acb-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="57acb-120">W aplikacji Supply Chain Management wybierz przycisk **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz w menu pozycję **Aplikacja mobilna**.</span><span class="sxs-lookup"><span data-stu-id="57acb-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="57acb-121">W oknie dialogowym **Zarządzaj aplikacją mobilną** znajdź kafelek **Zarządzanie składnikami majątku**.</span><span class="sxs-lookup"><span data-stu-id="57acb-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="57acb-122">Jeśli zawiera on tekst „W metadanych — nie opublikowano”, obszar roboczy nie został jeszcze opublikowany.</span><span class="sxs-lookup"><span data-stu-id="57acb-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="57acb-123">Jeśli zawiera on tekst „W metadanych — opublikowano”, obszar roboczy został już opublikowany, dlatego możesz pominąć pozostałą część tej procedury.</span><span class="sxs-lookup"><span data-stu-id="57acb-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="57acb-124">![Okno dialogowe zarządzania aplikacją mobilną](media/mobile-workspaces.png "Okno dialogowe zarządzania aplikacją mobilną")</span><span class="sxs-lookup"><span data-stu-id="57acb-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="57acb-125">Wybierz kafelek **Zarządzanie składnikami majątku**, a następnie wybierz pozycję **Publikuj** na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="57acb-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="57acb-126">Po kilku sekundach powinien zostać wyświetlony komunikat o pomyślnym opublikowaniu obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="57acb-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="57acb-127">Ponadto tekst na kafelku powinien się zmienić na „W metadanych — opublikowano”.</span><span class="sxs-lookup"><span data-stu-id="57acb-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="57acb-128">Instalowanie i konfigurowanie aplikacji mobilnej Finance and Operations (Dynamics 365)</span><span class="sxs-lookup"><span data-stu-id="57acb-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="57acb-129">Przejdź do jednego z następujących sklepów z aplikacjami, aby zainstalować aplikację **Microsoft Finance and Operations (Dynamics 365)** na urządzeniu przenośnym:</span><span class="sxs-lookup"><span data-stu-id="57acb-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="57acb-130">Dla urządzeń z systemem Android firmy Google</span><span class="sxs-lookup"><span data-stu-id="57acb-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="57acb-131">Dla urządzeń z systemem IOS firmy Apple</span><span class="sxs-lookup"><span data-stu-id="57acb-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="57acb-132">Otwórz aplikację Finance and Operations (Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="57acb-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="57acb-133">Powinna zostać wyświetlana strona logowania.</span><span class="sxs-lookup"><span data-stu-id="57acb-133">The sign-in page should appear.</span></span> <span data-ttu-id="57acb-134">W polu **Zaloguj się** wprowadź adres URL aplikacji Supply Chain Management lub wybierz ostatni adres URL z listy **Ostatnie środowiska**, a następnie naciśnij pozycję **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="57acb-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="57acb-135">![Strona logowania](media/mobile-app-sign-in.png "Strona logowania")</span><span class="sxs-lookup"><span data-stu-id="57acb-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="57acb-136">Jeśli zostanie wyświetlony monit o potwierdzenie połączenia, zaznacz pole wyboru **Rozumiem**, a następnie kliknij pozycję **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="57acb-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="57acb-137">Na stronie **Wybierz konto** użyj konta Microsoft, aby zalogować się do aplikacji na urządzenia mobilnej.</span><span class="sxs-lookup"><span data-stu-id="57acb-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="57acb-138">Zostanie wyświetlona strona **Obszary robocze**.</span><span class="sxs-lookup"><span data-stu-id="57acb-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="57acb-139">Zawiera listę wszystkich mobilnych obszarów roboczych, które zostały opublikowane przez wystąpienie aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="57acb-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="57acb-140">![Lista obszarów roboczych](media/mobile-app-workspaces.png "Lista obszarów roboczych")</span><span class="sxs-lookup"><span data-stu-id="57acb-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="57acb-141">Jeśli musisz zmienić osobę prawną (firmę), kliknij w lewym górnym rogu przycisk Menu (czasami określany jako menu lub przycisk typu „hamburger”) i kliknij pozycję **Zmień firmę**.</span><span class="sxs-lookup"><span data-stu-id="57acb-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="57acb-142">![Zmienianie osoby prawnej](media/mobile-app-change-comp.png "Zmienianie osoby prawnej")</span><span class="sxs-lookup"><span data-stu-id="57acb-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="57acb-143">Na stronie **Obszary robocze** wybierz obszar roboczy, z którym chcesz pracować, aby go otworzyć.</span><span class="sxs-lookup"><span data-stu-id="57acb-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="57acb-144">![Mobilny obszar roboczy zarządzania składnikami majątku](media/mobile-app-asset-workspace.png "Mobilny obszar roboczy zarządzania składnikami majątku")</span><span class="sxs-lookup"><span data-stu-id="57acb-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="57acb-145">Praca z mobilnym obszarem roboczym zarządzania składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="57acb-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="57acb-146">Aby uzyskać więcej informacji dotyczących pracy z mobilnym obszarem roboczym **Zarządzanie składnikami majątku**, zobacz temat [Korzystanie z mobilnego obszaru roboczego zarządzanie składnikami majątku](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="57acb-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="57acb-147">Aby uzyskać więcej informacji o aplikacji mobilnej Finance and Operations (Dynamics 365), zobacz [stronę główną aplikacji mobilnej](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="57acb-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]