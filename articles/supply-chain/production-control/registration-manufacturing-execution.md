---
title: Rejestracja w celu uruchomienia produkcji
description: W tym temacie opisano podstawowe pojęcia i terminy, które należy znać, aby prawidłowo skonfigurować moduł Wykonywanie produkcji i go używać.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bbcd7ebea869f921c2eadd05e64509ff9246aa4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "318173"
---
# <a name="registration-for-manufacturing-execution"></a>Rejestracja w celu uruchomienia produkcji

[!include [banner](../includes/banner.md)]

W tym temacie opisano podstawowe pojęcia i terminy, które należy znać, aby prawidłowo skonfigurować moduł Wykonywanie produkcji i go używać. 

Uruchomienie produkcji jest przeznaczone głównie do użycia przez firmy produkcyjne. Pracownicy mogą rejestrować czas i zużycie towarów dla zadań produkcji przy użyciu strony **Rejestracja zadania**. Wszystkie rejestracje są zatwierdzane i później przekazywane do odpowiednich modułów. Ciągłe zatwierdzanie i przenoszenie rejestracji pozwala menedżerom łatwo śledzić koszty rzeczywiste w zleceniach produkcyjnych.

## <a name="manufacturing-execution-and-registration-terminology"></a>Terminologia związana z uruchomieniem produkcji i rejestracją
Poniższa tabela zawiera terminy, które odnoszą się do uruchamiania produkcji i powiązanych zadań rejestracji.

| Okres                          | opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wykonywanie produkcji       | Funkcja używana do rejestrowania czasu, zużycia materiałów, kosztów w zadaniach produkcyjnych, projektów i działań pośrednich. Rejestracja jest wykonywana w kliencie rejestracji uruchomienia produkcji.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Lista zadań                      | Na stronie **Rejestracja zadania** pracownikom jest wyświetlana lista zadań, które muszą wykonać w stosunku do konkretnego zasobu, takiego jak maszyna. Pracownik może zarejestrować zużycie czasu i towaru dla poszczególnych zadań lub zadań na liście zadań.                                                                                                                                                                                                                                                                                                                                                                           |
| Tworzenie pakietów zadań                  | Jeśli pracownik uruchamia więcej niż jedno zadanie w tym samym czasie na stronie **Rejestracja zadania**, nazywa się to tworzeniem pakietów zadań. Czas przeznaczony na pakiety zadań można alokować do poszczególnych zadań na różne sposoby przy użyciu kluczy alokacji.                                                                                                                                                                                                                                                                                                                                                         |
| Rejestracje pilota/asystenta | Pracownik może się zarejestrować jako asystent do zasobu i utworzyć mały zespół, w którym kilku pracowników pracuje na tych samych zadaniach produkcyjnych. Zasoby, z którymi pracownicy są połączeni jako asystenci, są nazywane pilotami. Tylko zasób pilota musi wykonywać rejestracje. Wszyscy asystenci automatycznie uzyskują takie same dane rejestracyjne. Na przykład, jeśli maszyna działa jak pilot, pracownik, który zarejestrował się jako asystent do tej maszyny, może wprowadzać rejestracje na stronie **Rejestracja zadania**, a zarówno maszyna, jak i pracownicy połączeni jako asystenci, otrzymają takie same dane rejestracyjne. |
| Działanie pośrednie             | Czynność lub zadanie, które nie jest bezpośrednio związane z zadaniem produkcyjnym lub projektem, takie jak spotkanie pracowników działu, zadanie czyszczenia lub zadanie konserwacji w wydziale produkcyjnym. Pracownicy mogą wykonywać rejestracje działań pośrednich tak samo, jak rejestrują w projektach i zadaniach produkcyjnych.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Rejestracje w uruchomieniu produkcji
Pracownicy mogą wykonywać różne typy rejestracji w uruchomieniu produkcji dla pracy wykonanej w zadaniach produkcyjnych. W zależności od konfiguracji systemu, pracownicy mogą mieć możliwość rejestracji działań projektu i zadań nieprodukcyjnych, takich jak przerwy, działania pośrednie i nieobecności. Oto następujące typy rejestracji:

-   **Zarejestrowanie / wyrejestrowanie** (dostępne z modułu Czas i frekwencja) — pracownicy rejestrują się po przyjściu do pracy i wyrejestrowują, wychodząc do domu.
-   **Rejestrowanie w zadaniach produkcyjnych** – Pracownik może wykonać rejestracje, takie jak uruchamianie zadania i raportowanie informacji zwrotnej dla zadania w zadaniach produkcyjnych, które są wyświetlane na jego liście zadań. Pracownik może uruchomić kilka zadań jednocześnie. To działanie nazywane jest tworzeniem pakietów zadań.
-   **Rejestrowanie w magazynie** — Pracownik może wykonać rejestracje na materiałach użytych w wydziale produkcyjnym, które nie są bezpośrednio związane z zadaniami produkcyjnymi. Przykłady to smary, środki smarne lub inne materiały używane do utrzymywania maszyn w ruchu. Rejestracja jest wykonywana w arkuszu magazynowym.
-   **Rejestrowanie pracy przy projektach** (dostępne z modułu Czas i frekwencja) — pracownicy wprowadzają rejestracje, takie jak uruchamianie i kończenie pracy nad projektami lub działaniami w ramach projektu, które są wyświetlane na ich liście zadań.
-   **Rejestrowanie opłat w ramach projektu i elementów projektu** (dostępne z modułu Czas i frekwencja) — Pracownicy mogą rejestrować opłaty (wydatki) skojarzone z projektem w arkuszu opłat projektu, takie jak przebieg i myto. Pracownik może również zarejestrować zużycie towarów w projektach. Jest to wykonywane w arkuszu towarów projektu.
-   **Zarejestruj się jako asystent innego pracownika** — Jeśli dwóch lub więcej pracowników będzie współpracowało w zadaniu produkcyjnym lub projekcie, pracownik może się zarejestrować jako asystent maszyny lub innego pracownika, który będzie działać jako pilot. W razie potrzeby, pilot może wybrać innego pracownika jako pilota.
-   **Rejestrowanie nieobecności** (dostępne z modułu Czas i frekwencja) — pracownicy mogą rejestrować czas w różnych kodach nieobecności, które są skonfigurowane. Istnieje możliwość wskazania nieobecności, gdy pracownik się spóźnił, wymaga nieobecności w ciągu dnia pracy lub wychodzi wcześniej, niż oczekiwano zgodnie z profilem standardowego czasu pracy.
-   **Rejestrowanie przerw** (dostępne z modułu Czas i frekwencja) — w ciągu dnia pracy, pracownicy mogą rejestrować, że opuszczają stanowisko pracy, by zrobić sobie przerwę. Można skonfigurować kilka typów przerwy. Kiedy pracownik wraca i loguje się ponownie, system rejestruje, że pracownik wrócił i zatrzymuje rejestrację przerwy.
-   **Rejestrowanie pracy przy działaniach pośrednich** (dostępne z modułu Czas i frekwencja) — działania pośrednie to działania nieproduktywne, które pracownicy mogą wykonywać podczas dnia roboczego, takie jak spotkania pracowników działu, spotkania zespołu lub prace konserwacyjne w dziale produkcyjnym. Pracownicy mogą wykonywać rejestracje na skonfigurowanych działaniach pośrednich.
-   **Rejestrowanie nadgodzin** (dostępne z modułu Czas i frekwencja) — pracownik, którego poproszono o dłuższe godziny pracy może wybrać, czy nadgodziny mają być zarejestrowane jako elastyczny czas pracy czy jako nadgodziny.




