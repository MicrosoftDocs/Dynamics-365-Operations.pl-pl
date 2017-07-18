---
title: "Uzupełnianie zapasów"
description: "W tym temacie opisano strategie uzupełniania zapasów, które są dostępne dla magazynów używających funkcji dostępnych w module Zarządzanie magazynem."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: c3bbf35b98416cbc3feca2b0d01015a79cdb2659
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="replenishment"></a>Uzupełnianie zapasów

[!include[banner](../includes/banner.md)]


W tym temacie opisano strategie uzupełniania zapasów, które są dostępne dla magazynów używających funkcji dostępnych w module Zarządzanie magazynem. Informacje te nie mają zastosowania do aplikacji magazynowej dostępnej w module Zarządzanie zapasami. Dostępne są następujące strategie uzupełniania zapasów:

-   **Uzupełnianie popytu grupy czynności** — Ta strategia tworzy pracę uzupełniania dla zamówień lub ładunków wychodzących, gdy zapasy są niedostępne podczas tworzenia pracy przez grupę czynności. Na przykład pracę uzupełniania można utworzyć, jeśli ilość wymagana dla zamówienia sprzedaży nie jest dostępna w trakcie przetwarzania grupy czynności.
-   **Uzupełnianie według minimalnej/maksymalnej ilości** — Ta strategia wykorzystuje minimalne i maksymalne limity zapasów w celu określenia, kiedy należy uzupełnić lokalizacje. Kryteria towaru i lokalizacji definiują zapasy oceniane przy uzupełnianiu. Szablony uzupełniania zapasów według ilości minimalnej/maksymalnej są podstawowym mechanizmem utrzymywania optymalnego poziomu zapasów w lokalizacjach pobrania. Aby zagwarantować, że dostępna ilość rozpakowanych zapasów wystarcza do zaspokojenia popytu grupy czynności, można używać uzupełniania zapasów dla popytu dodatkowo między cyklami uzupełnienia według ilości minimalnej/maksymalnej.
-   **Uzupełnianie zapasów popytu ładunku** — Ta strategia sumuje popyt kilku ładunków i tworzy pracę uzupełniania niezbędną w celu dostarczenia zapasów do odpowiednich lokalizacji pobrania. Ta strategia pomaga zapewnić, że tworzone ładunki mogą po zwolnieniu zostać pobrane z magazynu.

Wszystkie trzy strategie tworzą pracę uzupełniania opartą na szablonie uzupełniania zapasów.

## <a name="wave-demand-replenishment"></a>Uzupełnianie popytu grupy czynności

Uzupełnianie popytu grupy czynności tworzy pracę uzupełniania na podstawie popytu, jeśli ilość wymagana dla zleceń produkcyjnych, kart Kanban, wychodzących zamówień lub ładunków nie jest dostępna podczas tworzenia pracy przez grupę czynności. Szablon uzupełniania zapasów zawiera informacje o kryteriach towaru, jednostce miary, przyroście popytu i lokalizacji. 

Dyrektywy lokalizacji są używane do określenia, w której lokalizacji mają być uzupełniane zapasy. Te dyrektywy lokalizacji łączy się z szablonem uzupełniania zapasów za pomocą pola **Kod dyrektywy**. Jeśli pole **Kod dyrektywy** nie jest ustawione, są używane zapytania do określenia, która dyrektywa lokalizacji ma być wykorzystywana. Należy zwrócić uwagę, że jeśli kod dyrektywy nie jest określony w szablonie uzupełniania zapasów, a dyrektywa lokalizacji ma kod dyrektywy, dyrektywa lokalizacji zostanie zignorowana, nawet jeśli zapytanie o dyrektywę lokalizacji jest poprawne. Dyrektywy lokalizacji pobrania są używane do określania, skąd pobrać zapasy dla uzupełnienia. 

Oprócz utworzenia szablonu grupy czynności należy też w nim określić pewne ustawienia uzupełniania zapasów. Szablon grupy czynności powinien zawierać krok grupy czynności uzupełniania, który będzie wykonywany tylko wtedy, gdy nie powiedzie się alokacja towaru. W tym kroku grupy czynności uzupełniania używa się kodu kroku grupy czynności w celu ustalenia, który szablon uzupełnienia zapasów powinien być używany. Oprócz utworzenia kroku grupy czynności uzupełniania zapasów należy się upewnić, że w szablonie grupy czynności w sekcji **Metody** jest zaznaczona wartość **Uzupełnianie zapasów**. 

Strona **Szablon uzupełniania** zawiera pole wyboru **Zezwalaj na używanie niezarezerwowanych ilości z powodu popytu grupy czynności**. Należy zaznaczyć to pole wyboru, jeśli uzupełnianie zapasów dla popytu ma odejmować niezarezerwowane ilości z pracy wygenerowanej przy użyciu wybranego szablonu uzupełniania zapasów. Aby szablony uzupełniania zapasów popytu mogły korzystać z tej logiki, to pole wyboru musi być zaznaczone dla każdego istniejącego szablonu uzupełniania zapasów. Po uruchomieniu funkcji uzupełnienia zapasów dla popytu w magazynie odejmie ona popyt od istniejącej pracy uzupełniania zapasów, która ma niezarezerwowane ilości, jeśli praca pochodzi z szablonów uzupełniania zapasów, dla których zaznaczono pole wyboru **Zezwalaj na używanie niezarezerwowanych ilości z powodu popytu grupy czynności**.


Uzupełnienie zapasów popytu jest obsługiwane w przypadku zamówień sprzedaży, zamówień przeniesienia, zleceń produkcyjnych i kart Kanban. 

## <a name="minmax-replenishment"></a>Uzupełnianie według minimalnej/maksymalnej ilości
W uzupełnianiu według minimalnej/maksymalnej ilości zapasy są uzupełniane w taki sposób, aby znajdowały się między ustawioną minimalną i maksymalną wartością graniczną. Zazwyczaj ten proces występuje raz każdego dnia, aby zagwarantować, że wszystkie lokalizacje pobrania są wypełnione do maksymalnego poziomu przed rozpoczęciem pobierania. 

Minimalne i maksymalne kwoty są ustawiane w szablonie uzupełniania zapasów. Wiele innych ustawień w szablonie przypomina ustawienia w szablonach używanych do uzupełniania popytu grupy czynności. Ten szablon powinien zawierać jeden wiersz dla każdego towaru i lokalizacji. Po uruchomieniu uzupełniania zapasów przy użyciu zadania wsadowego program Finance and Operations ocenia, czy uzupełnianie zapasów jest wymagane, w kolejności ułożenia wierszy. 

Należy zwrócić uwagę, strategia uzupełniania według ilości minimalnej/maksymalnej nie może uzupełniać pustej lokalizacji, chyba że lokalizacja jest ustawiona jako stała lokalizacja dla towaru. Jeśli lokalizacja przeznaczona do uzupełniania nie jest stałą lokalizacją, nie można ustalić, który towar ma być uzupełniany. W związku z tym przed rozpoczęciem uzupełniania musi istnieć co najmniej pewna ilość dostępna.

## <a name="load-demand-replenishment"></a>Uzupełnianie zapasów popytu ładunku
Strategia uzupełniania zapasów popytu ładunku sumuje popyt kilku ładunków i tworzy pracę uzupełniania niezbędną w celu dostarczenia zapasów do odpowiednich lokalizacji pobrania. Pod wieloma względami uzupełnianie zapasów popytu ładunku przypomina uzupełnianie popytu grupy czynności. Główna różnica polega na tym, jak i kiedy są uruchamiane oba rodzaje uzupełniania. Podobnie jak uzupełnianie według minimalnej/maksymalnej ilości, uzupełnianie zapasów popytu ładunku jest wykonywane przy użyciu zadania wsadowego. Aby skonfigurować zadanie wsadowe, na stronie **Uzupełnianie zapasów popytu ładunku** wybierz szablon uzupełniania zapasów, który ma być używany, i ustaw zapytanie filtrujące, aby określić, które ładunki będą używane do określania popytu. Zapytanie o lokalizację zdefiniuje lokalizacje, z których będą odejmowane wszelkie dostępne ilości, aby zaspokoić zagregowany popyt ładunków.

## <a name="replenishment-prerequisites"></a>Warunki wstępne uzupełniania zapasów
| Wymaganie wstępne            | Opis                                                                                                                                                                                                                                        |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pozycja                    | Dla danego towaru musi być możliwa obsługa zarządzania magazynem.                                                                                                                                                                                       |
| Magazyn               | Musi być możliwe zarządzanie danym magazynem. Aby włączyć magazyn dla procesów zarządzania magazynem, na stronie **Magazyny** wybierz magazyn, a następnie zaznacz opcję **Użyj procesów zarządzania magazynami**. |
| Szablony uzupełniania zapasów | Musi być skonfigurowany co najmniej jeden szablon uzupełnienia według minimalnej/maksymalnej ilości, uzupełniania popytu grupy czynności lub uzupełniania zapasów popytu ładunku.                                                                                                             |
| Lokalizacje               | Lokalizacje muszą być utworzone i połączone z profilem lokalizacji.                                                                                                                                                                                     |
| Profile lokalizacji       | Profile lokalizacji są wymagane w celu utworzenia lokalizacji.                                                                                                                                                                                       |
| Dyrektywy lokalizacji     | Dyrektywy lokalizacji są wymagane w celu skierowania pracy do lokalizacji, w których jest wymagane uzupełnianie zapasów i z których będą pobierane zapasy.                                                                                     |
| Szablony pracy          | Szablony pracy typu **Uzupełnianie zapasów** są wymagane w celu utworzenia pracy uzupełniania zapasów, która spowoduje przeniesienie zapasów do żądanych lokalizacji.                                                                                           |

