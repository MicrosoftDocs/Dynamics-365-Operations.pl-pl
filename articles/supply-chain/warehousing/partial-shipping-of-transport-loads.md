---
title: Częściowa dostawa ładunku w transporcie
description: W tym temacie wyjaśniono, jak można częściowo wysłać ładunek i odłożyć planowania pojemności dla ładunku.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8c172f1b66e56f60e89f56ea98910f8d0e4f3e36
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545274"
---
# <a name="partial-shipment-of-a-transport-load"></a>Częściowa dostawa ładunku w transporcie

[!include[banner](../includes/banner.md)]

Konfigurując częściową wysyłkę ładunków, można obsługiwać ładunki, gdy pojemność daje się określić dopiero po dodaniu wszystkich wierszy sprzedaży do ładunku. Następnie, gdy jest znana dokładna liczba palet, można sfinalizować proces. Dzięki temu nie trzeba decydować, które palety zostaną przypisane do którego transportu, aż do chwili, gdy transport zostanie fizycznie załadowany z przygotowanych zapasów.

Ta funkcja oferuje alternatywę wobec egzekwowania bardziej sztywnej struktury, gdzie trzeba określić, które palety zostaną przypisane do którego transportu, zanim będzie można utworzyć pracę pobrania lub załadunku. Zamiast tego użytkownicy mogą skonfigurować poszczególne ładunki na potrzeby potwierdzenia dostawy częściowej. Wtedy mogą nastąpić procesy umieszczenia tych ładunków w środku transportu ładunku. Dzięki temu dział planowania transportu może planować ładunki bez konieczności brania pod uwagę pojemności poszczególnych transportów.

W momencie załadunku pracownicy mogą zdefiniować nowy środek transportu ładunku, do którego można załadować paletę. Alternatywnie mogą wskazać istniejący środek transportu ładunku. Te dane można rejestrować za pomocą urządzenia przenośnego. W efekcie kilku pracowników magazynu może ładować zapasy z tych samych lub różnych ładunków na tę samą ciężarówkę. Następnie ładunki można w pełni lub częściowo wysłać.

> [!NOTE] 
> Aby załadować zapasy z ładunku do konkretnego środka transportu ładunku i częściowo wysłać, należy wygenerować pracę, używając klasy załadunku w szablonie pracy. Zwykła praca pobrania o typie **Pobranie** nie może służyć do ładowania do środka transportu ładunku, takiego jak ciężarówka.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Konfigurowanie środków transportu ładunku dla wysyłki częściowej

Konfiguracja częściowej wysyłki ładunki składa się z dwóch poniższych procedur.

### <a name="set-the-loading-strategy"></a>Konfigurowanie strategii załadunku

Należy włączyć załadunek częściowy poprzez ustawienie strategii załadunku. Strategię załadunku można ustawić po utworzeniu ładunku.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ładunki** \> **Wszystkie ładunki**.
2. Wybierz ładunek i kliknij opcję **Nagłówek**.
3. W polu **Strategia ładowania** zaznacz opcję **Dozwolona częściowa wysyłka ładunku**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Tworzenie elementu menu dla załadunku na środki transportu ładunku

Należy utworzyć nowy element menu, który umożliwi załadunek na środki transportu ładunku. Środek transportu ładunku pozwala grupować wiersze pracy z jednego ładunku lub wielu ładunków. Wszystko, co zostanie dodane do środka transportu ładunku, można następnie wysłać przy użyciu skanera przenośnego.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.
2. Wybierz opcję **Nowy**, a następnie w polu **Tryb** wybierz opcję **Praca**.
3. W opcji **Użyj istniejącej pracy** zaznacz wartość **Tak**.
4. Na karcie **Ogólne** w polu **Sterowane przez** wybierz opcję **Ładowanie transportu**.
5. Aby włączyć potwierdzania wysyłki na przenośnym skanerze, w polu **Dozwolony typ potwierdzenia wysyłki** wybierz opcję **Ładunek w transporcie**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Potwierdzanie wysyłki środka transportu ładunku z klienta

Ta konfiguracja umożliwia potwierdzenie środka transportu ładunku, który zawiera ładunek pełny lub częściowy przeznaczony do wysłania.

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ładunki** \> **Ładunki w transporcie**.
2. W okienku akcji na karcie **Wyślij i odbierz** w grupie **Potwierdź** kliknij opcję **Transport**.
