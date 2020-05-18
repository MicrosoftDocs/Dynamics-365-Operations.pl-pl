---
title: Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej
description: W tym temacie opisano sposób konfigurowania aplikacji magazynowej w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346383"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a><span data-ttu-id="40506-103">Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="40506-103">License plate receiving via the warehousing app</span></span>

<span data-ttu-id="40506-104">W tym temacie opisano sposób konfigurowania aplikacji magazynowej w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.</span><span class="sxs-lookup"><span data-stu-id="40506-104">This topic explains how to set up the warehousing app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="40506-105">Ta funkcja służy do szybkiego rejestrowania przyjęcia przychodzącego zapasu, który jest powiązany z zawiadomieniem o zaliczce na poczet wysyłki (ASN).</span><span class="sxs-lookup"><span data-stu-id="40506-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="40506-106">System automatycznie tworzy ASN, gdy procesy zarządzania magazynem służą do wysłania zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="40506-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="40506-107">W procesie zamówienia zakupu można ręcznie zarejestrować ASN lub można go zaimportować automatycznie za pomocą procesu przychodzącej jednostki danych ASN.</span><span class="sxs-lookup"><span data-stu-id="40506-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="40506-108">Dane ASN są połączone z ładowaniem i wysyłkami za pośrednictwem *struktur pakowania*, w których palety (nadrzędne numery identyfikacyjne) mogą zawierać sprawy (zagnieżdżone numery identyfikacyjne).</span><span class="sxs-lookup"><span data-stu-id="40506-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="40506-109">Aby zmniejszyć liczbę transakcji magazynowych, gdy używane są struktury opakowań z zagnieżdżonymi numerami identyfikacyjnymi, system rejestruje fizycznie dostępne zapasy na nadrzędnym numerze identyfikacyjnym.</span><span class="sxs-lookup"><span data-stu-id="40506-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="40506-110">Aby wyzwolić przesunięcie fizycznego stanu zapasów z nadrzędnego numeru identyfikacyjnego do zagnieżdżoneego numeru identyfikacyjnego na podstawie danych o strukturze pakowania, urządzenie przenośne musi dostarczyć element menu, który jest oparty procesie tworzenia pracy *Pakowanie do zagnieżdżonych numerów identyfikacyjnych*.</span><span class="sxs-lookup"><span data-stu-id="40506-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="40506-111">Wyświetlanie lub pomijanie strony Podsumowanie przyjęcia</span><span class="sxs-lookup"><span data-stu-id="40506-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="40506-112">Funkcji *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych* można użyć w celu wykorzystania dodatkowego przepływu aplikacji magazynowej w ramach procesu odbierania numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="40506-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed warehousing app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="40506-113">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="40506-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="40506-114">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="40506-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="40506-115">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="40506-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="40506-116">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="40506-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="40506-117">**Nazwa funkcji:** *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych*</span><span class="sxs-lookup"><span data-stu-id="40506-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="40506-118">Gdy ta funkcja jest włączona, pozycje menu urządzenia mobilnego dotyczące odbioru i odłożenia tablicy rejestracyjnej oraz odłożenia tablicy rejestracyjnej będą zapewniać ustawienie **Wyświetl stronę podsumowania przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="40506-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="40506-119">To ustawienie ma następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="40506-119">This setting has the following options:</span></span>

- <span data-ttu-id="40506-120">**Wyświetlenie szczegółowego podsumowania** — podczas przyjmowania numeru identyfikacyjnego pracownicy będą widzieć dodatkową stronę, na której są wyświetlane pełne informacje dotyczące ASN.</span><span class="sxs-lookup"><span data-stu-id="40506-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="40506-121">**Pomiń podsumowanie** — pracownicy nie będą widzieli pełnych informacji ASN.</span><span class="sxs-lookup"><span data-stu-id="40506-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="40506-122">Pracownicy magazynu również nie będą mogli ustawić kodu dyspozycji ani dodać wyjątków podczas procesu odbioru.</span><span class="sxs-lookup"><span data-stu-id="40506-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="40506-123">Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy</span><span class="sxs-lookup"><span data-stu-id="40506-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="40506-124">Nie można użyć procesu odbierania numeru identyfikacyjnego, jeśli numer ASN zawiera identyfikator numeru identyfikacyjnego, który już istnieje, i zawiera fizyczne dostępne dane w lokalizacji magazynowej innej niż lokalizacja magazynu, w którym występuje rejestracja numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="40506-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="40506-125">W scenariuszach zamówień przeniesienia, w których magazyn tranzytowy nie śledzi numerów identyfikacyjnych (a zatem nie śledzi fizycznych dostępnych zapasów powiązanych z numerem identyfikacyjnym), można użyć funkcji *Zapobiegaj wykorzystywaniu wysłanych numerów identyfikacyjnych z zamówień przeniesienia w magazynach innych niż magazyn docelowy* w celu uniemożliwienia fizycznej aktualizacji numerów identyfikacyjnych w tranzycie.</span><span class="sxs-lookup"><span data-stu-id="40506-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="40506-126">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="40506-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="40506-127">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="40506-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="40506-128">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="40506-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="40506-129">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="40506-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="40506-130">**Nazwa funkcji:** *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy*</span><span class="sxs-lookup"><span data-stu-id="40506-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="40506-131">Aby zarządzać funkcjami, gdy ta funkcja jest dostępna, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="40506-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="40506-132">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="40506-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="40506-133">Na karcie **Ogólne**, na skróconej karcie **Numery identyfikacyjne** w polu **Zasady dotyczące numerów identyfikacyjnych magazynu tranzytowego** określ jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="40506-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="40506-134">**Zezwalaj na ponowne użycie nieśledzonego numeru identyfikacyjnego** — system działa tak samo, jak działa, gdy funkcja *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy* nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="40506-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="40506-135">Ta wartość jest ustawieniem domyślnym przy pierwszej aktywacji funkcji.</span><span class="sxs-lookup"><span data-stu-id="40506-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="40506-136">**Zapobiegaj ponownemu użyciu nieśledzonych numerów identyfikacyjnych** — w magazynie docelowym będą dozwolone tylko aktualizacje stanu zapasów związane ze wysyłką numeru identyfikacyjnego, dopóki zamówienie przeniesienia nie zostanie odebrane.</span><span class="sxs-lookup"><span data-stu-id="40506-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="40506-137">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="40506-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="40506-138">Aby uzyskać więcej informacji o elementach menu urządzeń przenośnych, zapoznaj się z tematem [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="40506-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
