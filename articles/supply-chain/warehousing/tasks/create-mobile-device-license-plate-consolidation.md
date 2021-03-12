---
title: Tworzenie elementu menu urządzenia przenośnego dla konsolidacji na podstawie numerów identyfikacyjnych
description: Ta procedura pokazuje, jak utworzyć element menu urządzenia przenośnego dla pracy konsolidacji na podstawie numerów identyfikacyjnych.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3f5f572461de007f137ffa7ea05c535371f95b7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977245"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a>Tworzenie elementu menu urządzenia przenośnego dla konsolidacji na podstawie numerów identyfikacyjnych

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak utworzyć element menu urządzenia przenośnego dla pracy konsolidacji na podstawie numerów identyfikacyjnych. Dzięki temu pracownicy magazynu będą mogli konsolidować towary o jednym numerze identyfikacyjnym z towarami o innym numerze identyfikacyjnym w tej samej lokalizacji. Na przykład mogą używać tej funkcji, jeżeli kolejne kroki przygotowania były takie same w obu zleceniach i pracę można wykonać tylko raz dla scalonych towarów. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. To zadanie zazwyczaj wykonuje kierownik magazynu. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.
2. Kliknij przycisk Nowy.
3. W polu Nazwa elementu menu wpisz wartość.
4. W polu Tytuł wpisz wartość.
5. W polu Tryb wybierz opcję „Pośrednie”.
6. W polu Kod działania wybierz opcję „Konsoliduj numery identyfikacyjne”.

