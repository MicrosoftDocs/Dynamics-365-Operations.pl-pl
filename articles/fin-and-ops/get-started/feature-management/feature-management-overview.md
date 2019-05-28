---
title: Zarządzanie funkcjami — omówienie
description: W tym temacie opisano funkcję zarządzania funkcjami i sposób jego używania.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538705"
---
# <a name="feature-management-overview"></a>Zarządzanie funkcjami — omówienie

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Funkcje są dodawane i aktualizowane w każdym wydaniu Microsoft Dynamics 365 for Finance and Operations. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.

## <a name="the-feature-management-workspace"></a>Obszar roboczy Zarządzanie funkcjami

Obszar roboczy **zarządzanie funkcjami** można otworzyć, wybierając odpowiedni kafelek na pulpicie nawigacyjnym. Zobaczysz stronę, która zawiera listę funkcji dla wszystkich wersji, które są obsługiwane przez funkcję zarządzania funkcjami. Z biegiem czasu firma Microsoft zwiększy funkcjonalność zarządzania funkcjami, tak aby były dostępne dodatkowe funkcje do łatwiejszego zarządzania funkcjami.

Lista funkcji zawiera następujące informacje:

- **Nazwa funkcji** — opis dodanej funkcji.
- **Stan włączony** — symbol wskazuje, czy funkcja została włączona (znacznik wyboru), nie jest włączona (pusta), została zaplanowana do włączenia (zegar) lub jest obowiązkowa (blokada). Pokazane tutaj ustawienie jest używane dla wszystkich firm. Należy pamiętać, że nawet wtedy, gdy funkcja została włączona, jest nadal kontrolowana przez zabezpieczenia. W związku z tym funkcja będzie dostępna tylko dla użytkowników, którzy mają do niej dostęp, na podstawie ich roli zabezpieczeń. Będzie ona również dostępna tylko dla osób prawnych, do których użytkownik ma dostęp.
- **Data włączenia** — data, kiedy funkcja została włączona lub zostanie włączona, jeśli data jest datą przyszłą.
- **Dodano funkcję** – data, kiedy funkcja została dodana do danego środowiska. Ta data jest automatycznie wprowadzana podczas aktualizowania środowiska podczas comiesięcznych wydań.
- **Moduł** — moduł, którego dotyczy nowa funkcja.

Po wybraniu funkcji w okienku szczegółów po prawej stronie listy funkcji pojawią się dodatkowe informacje. W górnej części okienka zobaczysz nazwę funkcji, datę dodania funkcji, moduł, którego dotyczy ta funkcja, oraz łacze **Dowiedz się więcej**. Wybierz to łącze, aby wyświetlić dokumentację dla tej funkcji. Jeśli dokumentacja nie jest dostępna, nastąpi przekierowanie na stronę tymczasową. Okienko szczegółów zawiera również pole **komentarzy**, w którym można dodawać własne komentarze dotyczące tej funkcji.

Obszar roboczy **zarządzanie funkcjami** zawiera również kilka kart z listą funkcji. 
- **Nowość** - pokazuje wszystkie funkcje, które zostały dodane od czasu ostatniej aktualizacji miesięcznej. Jeśli użytkownik pominął comiesięczne aktualizacje, w obszarze nowość będą wszystkie nowe funkcje od czasu ostatniej aktualizacji. Najnowsze funkcje są wyświetlane na górze listy. Całkowita liczba nowych funkcji jest również wyświetlana na kafelku u góry strony.
- **Nie włączono** - pokazuje wszystkie funkcje, które nie zostały włączone. Najnowsze funkcje są wyświetlane na górze listy. Całkowita liczba nowych funkcji jest również wyświetlana na kafelku u góry strony.
- **Zaplanowane** — pokazuje wszystkie funkcje, które zostały zaplanowane do włączenia w przyszłości. Funkcje, które mają najwcześniejszą zaplanowaną datę pojawią się u góry listy. Całkowita liczba nowych funkcji jest również wyświetlana na kafelku u góry strony.
- **Wszystkie** - pokazuje wszystkie funkcje. Najnowsze funkcje są wyświetlane na górze listy.


## <a name="enable-a-feature"></a>Włączanie funkcji

Jeśli funkcja nie została włączona, w okienku szczegółów zostanie wyświetlony przycisk **Włącz**. Za pomocą tego przycisku można włączyć tę funkcję.

1. Wybierz funkcję, którą chcesz włączyć, a następnie w okienku szczegółów wybierz pozycję **Włącz.**
2. Pojawi się suwak, w którym można określić datę włączenia tej funkcji. Domyślnie suwak jest ustawiony na bieżącej dacie.
3. Wybierz **Włącz**, aby włączyć tę funkcję.

Niektóre funkcje nie mogą być wyłączone po ich włączeniu. Jeśli funkcja, którą próbujesz włączyć, nie może być wyłączona, pojawi się ostrzeżenie. W tym momencie możesz wybrać **Anuluj**, aby anulować operację i pozostawić tę funkcję wyłączoną. Jeśli jednak wybierzesz opcję **Włącz** i włączysz tę funkcję, nie będzie można jej później wyłączyć.

Po włączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat informuje, że funkcja została włączona lub wskazuje, kiedy funkcja zostanie włączona w przyszłości. Jeśli korzystasz z przyszłej daty, funkcja będzie wyświetlana na liście **zaplanowane.** Ta wiadomość pojawi się za każdym razem, gdy wybierzesz operację na liście funkcji. Funkcje zaplanowane w przyszłości zostaną włączone o północy przez proces wsadowy na podstawie strefy czasowej reprezentowanej przez datę systemową. 

## <a name="reschedule-a-feature"></a>Zmiana harmonogramu funkcji

Jeśli dla funkcji ustawiono przyszłą datę włączenia, w okienku szczegółów zostanie wyświetlony przycisk **Przeplanuj**. Można użyć tego przycisku, aby zmienić datę **włączenia**.

1. Wybierz zaplanowaną funkcję, której datę włączenia chcesz zmienić, a następnie w okienku szczegółów wybierz pozycję **Przeplanuj.**
2. Pojawi się suwak, w którym można określić datę włączenia tej funkcji. 
3. Wybierz opcję **Włącz**, aby ponownie zaplanować operację lub **wyłącz**, aby anulować harmonogram.

## <a name="disable-a-feature"></a>Wyłączanie funkcji

Jeśli funkcja została już włączona, w okienku szczegółów zostanie wyświetlony przycisk **Wyłącz**. Za pomocą tego przycisku można wyłączyć tę funkcję. Przycisk **Wyłącz** jest niedostępny, jeśli po włączeniu tej funkcji nie można jej wyłączyć.

- Wybierz funkcję, którą chcesz wyłączyć, a następnie w okienku szczegółów wybierz pozycję **Wyłącz.**

- Funkcja jest wyłączona, a data jest wyczyszczona.

Po wyłączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat stwierdza, że funkcja nie została jeszcze włączona i pojawi się na liście **Niewłączone**. Ta wiadomość pojawi się za każdym razem, gdy wybierzesz operację na liście funkcji.

## <a name="features-that-must-be-enabled"></a>Funkcje, które muszą być włączone

Może zostać dostarczona krytyczna funkcja, która musi być włączona automatycznie po wykonaniu aktualizacji. Zostanie ona automatycznie włączona w dniu **włączenia.** Pod łączem **Dowiedz się więcej** w okienku szczegółów pojawi się komunikat. Ten komunikat będzie informował, że funkcja została włączona lub zostanie włączona automatycznie w **dniu włączenia**. Ta wiadomość pojawi się za każdym razem, gdy wybierzesz operację na liście funkcji.

## <a name="assigning-roles"></a>Przypisywanie ról

Obszar roboczy **zarządzanie funkcjami** mogą otwierać administratorzy systemu i użytkownicy przypisani do Menedżera funkcji lub ról podglądu funkcji utworzonych w celu obsługi środowiska zarządzania funkcją. Użytkownicy w roli Menedżera funkcji mogą włączać i wyłączać dowolne funkcje. Mogą również aktualizować sekcję komentarzy dla tej funkcji. Użytkownicy w roli podglądu funkcji mogą wyświetlać tylko obszar roboczy **zarządzanie funkcją**. Nie mogą włączać ani wyłączać funkcji.

Rola Menedżera funkcji i roli podglądu funkcji nie zastępują istniejących zabezpieczeń przypisanych do użytkownika. Role kontrolują tylko dostęp do funkcji włączania. Nie zapewniają dostępu do samych funkcji.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Korzystanie z funkcji zarządzania funkcjami w celu włączania funkcji ISV lub funkcji niestandardowych

Proces zarządzania funkcjami nie jest obecnie dostępny dla funkcji ISV lub funkcji niestandardowych. Dodajemy dodatkowe funkcje w celu usprawnienia zarządzania funkcjami i, gdy te ulepszenia są kompletne, będziemy poszerzać Zarządzanie funkcjami na wszystkie funkcje i dostarczyć szczegółowe instrukcje, jak zaktualizować swoją funkcję, aby korzystać z tej możliwości.

## <a name="feature-management-and-flighting"></a>Zarządzanie funkcją i dystrybucja testowa

Zarządzanie funkcjami umożliwia kontrolowanie funkcji, które są dostarczane w każdej wersji. Dystrybucja testowa umożliwia zespołom firmy Microsoft udostępnianie funkcji ograniczonej liczbie klientów, dzięki czemu funkcje mogą być testowane i weryfikowane bez wpływu na wszystkich klientów. Zarządzanie funkcjami nie kontroluje dystrybucji testowej żadnych funkcji.
