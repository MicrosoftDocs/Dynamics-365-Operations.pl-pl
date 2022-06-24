---
title: Aktualizuj śledzenie do odłożenia
description: W tym artykule opisano sposób konfigurowania i uruchamiania zadania okresowego aktualizacji śledzenia dla odłożenia.
author: Weijiesa
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b36fe5a9828ea018881f08b8af27d77cdf0babc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882613"
---
# <a name="update-tracking-for-put-away"></a>Aktualizuj śledzenie do odłożenia

[!include [banner](../includes/banner.md)]

Zadanie okresowe *Aktualizuj śledzenie do odłożenia* jest przeznaczone do uruchamiania w nocy jako cykliczne zadanie wsadowe. Określa, które podróże otrzymały wszystkie transakcje inwentaryzacji, a które podróży nie mają wartości dla rzeczywistej daty zakończenia. Następnie ustawia rzeczywistą datę zakończenia na bieżącą datę zgodnie z wymaganiami.

*Działania kontenerów* są tworzone dla każdego *etapu* podróży dla każdego *kontenera wysyłkowego*. Wartości te są definiowane przez szablon podróży wybrany podczas tworzenia podróży. Dla każdego rekordu działań kontenera można ustawić wartości dla pól **Data rozpoczęcia**, **Szacowana data zakończenia** i **Rzeczywista data zakończenia**. Pola te można zaktualizować po otrzymaniu potwierdzenia, że etap został rozpoczęty lub zakończony.

Zazwyczaj informacje związane z potwierdzonymi datami są dostarczane przez inną firmę, na przykład spedytora, ponieważ te akcje są obsługiwane poza aplikacją Microsoft Dynamics 365 Supply Chain Management. Jednak informacje od innej firmy nie są wymagane do śledzenia przybycia towarów z etapu podróży do magazynu (oznaczonego przez odłożenie towarów). W związku z tym śledzenie można określić na podstawie informacji w aplikacji Dynamics 365 Supply Chain Management.

Aby skonfigurować i uruchomić zadanie okresowe *Aktualizuj śledzenie do odłożenia*, wykonaj następujące kroki:

1. Przejdź do pozycji **Koszt z wyładunkiem \> Zadania okresowe \> Aktualizuj śledzenie do odłożenia**.
1. W oknie dialogowym **Aktualizuj śledzenie do odłożenia** w sekcji **Parametry** ustaw następujące pola:

    - **Etap** — wybierz unikatową nazwę identyfikacyjną/numer dla części podróży, dla której chcesz zaktualizować śledzenie. Wybrana wartość musi odzwierciedlać przybycie z podróży do magazynu.
    - **Działanie** — wybierz działanie, które zostało podjęte podczas wybranego etapu. Wartości te są przypisywane dla wiersza szablonu podróży w centrum sterowania śledzeniem.

1. Aby ograniczyć zestaw rekordów do uwzględnienia w aktualizacji, na skróconej karcie **Rekordy do uwzględnianie** wybierz przycisk **Filtruj**. Zostanie wyświetlone standardowe okno dialogowe zapytania, w którym można definiować kryteria wyboru, kryteria sortowania i sprzężenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w module Supply Chain Management. Pola w tym miejscu są tylko do odczytu i pokazują wartości, które są powiązane z zapytaniem.
1. Na skróconej karcie **Uruchom w tle** skonfiguruj wymagane opcje przetwarzania wsadowego i planowania, tak jak w przypadku innych typów zadań w aplikacji Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i uruchomić lub zaplanować aktualizację.
