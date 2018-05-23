---
title: "Omówienie Doradcy optymalizacji"
description: "W tym temacie opisano, jak za pomocą Doradcy optymalizacji uzyskać optymalną konfigurację programu Microsoft Dynamics 365 Finance and Operations."
author: roxanadiaconu
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core (Operations, Core)
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c055c673443255f3e6dda5e1179e1ef28d90e693
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="optimization-advisor-overview"></a>Omówienie Doradcy optymalizacji

[!INCLUDE [banner](../includes/banner.md)]

W tym temacie opisano, jak za pomocą Doradcy optymalizacji uzyskać optymalną konfigurację programu Microsoft Dynamics 365 Finance and Operations.

## <a name="overview"></a>Przegląd

Niepoprawna konfiguracja i instalacja modułu mogą negatywnie wpływać na dostępność funkcji w programie Finance and Operations, wydajność systemu oraz przebieg procesów biznesowych. Również jakość danych biznesowych (na przykład poprawność, kompletność i czystość danych) wpływają na wydajność systemu, zdolność podejmowania decyzji w organizacji, wydajność pracy itd.

Obszar roboczy **Doradca optymalizacji** jest narzędziem, które pozwala użytkownikom zaawansowanym, analitykom biznesowym, konsultantom funkcjonalnym i personelowi wsparcia IT wykrywać problemy w konfiguracji modułu i danych biznesowych. Doradca optymalizacji sugeruje najlepsze praktyki dotyczące konfiguracji modułu oraz identyfikuje dane biznesowe, które są nieaktualne lub zawierają błędy.

Doradca optymalizacji co pewien czas uruchamia zbiór zasad najlepszego rozwiązania. Domyślny zestaw reguł został opublikowany razem z programem Microsoft Dynamics 365 for Finance and Operations w wersji 8.0 (z kwietnia 2018 r.). Jednak użytkownicy mogą również tworzyć reguły dotyczące ich konkretnych personalizacji, rozwiązań od niezależnych dostawców oprogramowania (ISV) i danych biznesowych. Aby uzyskać więcej informacji dotyczących sposobu tworzenia reguł, zobacz [Tworzenie nowych reguł](./create-rules-optimization-advisor.md).

Po wykryciu naruszenia reguły jest generowana możliwość optymalizacji i pojawia się ona w obszarze roboczym **Doradca optymalizacji**. Użytkownik może podjąć odpowiednie czynności naprawcze bezpośrednio z obszaru roboczego **Doradca optymalizacji**.

Możliwości mogą być związane z konkretną firmą lub międzyfirmowe, w zależności od typu instalacji i rodzaju sprawdzanych danych. Możliwości międzyfirmowe można wyświetlać we wszystkich firmach. Aby wyświetlić możliwości dla określonej firmy, należy najpierw zaznaczyć tę firmę.

Do możliwości optymalizacji stosuje się standardowe zasady zabezpieczeń. Na przykład możliwości optymalizacji związane z konfiguracją modułu **Zarządzanie magazynem** są widoczne tylko dla użytkowników, którzy mają dostęp do tego modułu i mogą zmieniać jego ustawienia.

Podczas wykonywania operacji na niektórych możliwościach optymalizacji system oblicza wpływ możliwości pod względem skrócenia czasu wykonywania procesów biznesowych. Niestety, ta funkcja nie jest dostępna dla wszystkich możliwości optymalizacji.

Aby uzyskać więcej informacji o Doradcy optymalizacji, obejrzyj krótki film [Doradca optymalizacji w programie Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

> [!Video https://www.youtube.com/embed/MRsAzgFCUSQ]

## <a name="optimization-rules"></a>Reguły optymalizacji

Aby wyświetlić pełną listę reguł Doradcy optymalizacji i zobaczyć, jak często ich przestrzeganie jest weryfikowane, wybierz kolejno opcje **Administrowanie systemem** &gt; **zadania okresowe** &gt; **Obsługa reguły weryfikacji diagnostyki**. Sprawdzane jest tylko przestrzeganie reguł znajdujących się w stanie **Aktywne**. Można ustawić częstotliwość sprawdzania **Codziennie**, **Co tydzień**, **Co miesiąc** lub **Nie zaplanowano**.

Aby zainicjować sprawdzanie przestrzegania reguł niezaplanowanych lub ponowne sprawdzić przestrzeganie reguł okresowych poza ich wstępnie zdefiniowanym harmonogramem, wybierz kolejno opcje **Administrowanie systemem** &gt; **Zadania okresowe** &gt; **Planowanie reguły weryfikacji diagnostyki**. Następnie w oknie dialogowym **Weryfikacja reguł diagnostyki** wybierz częstotliwość weryfikacji. Wszystkie reguły mające podaną częstotliwość zostaną ponownie sprawdzone.

Obecny zestaw reguł optymalizacji można podzielić na następujące kategorie.

### <a name="module-configuration-and-setup"></a>Instalacja i konfiguracja modułu

Instalowanie modułu Zarządzanie magazynem to skomplikowany proces. Aby ułatwić ten proces, wprowadzono pewne reguły sprawdzające poprawność instalacji. Na przykład jedna reguła sprawdza poprawność ustawień dyrektyw lokalizacji w magazynie dla stałych lokalizacje wariantów produktów na potrzeby zamówień sprzedaży i zamówień przeniesienia.

Inne reguły sprawdzają, czy włączone funkcje są rzeczywiście używane. Na przykład jedna reguła ustala, czy jest wykorzystywany moduł **Planowanie główne**. Jeśli reguła stwierdzi, że nie używasz tego modułu, zostanie wygenerowana możliwość optymalizacji sugerująca wyłączenie procesów planowania.

### <a name="system-configuration"></a>Konfiguracja systemu

Jeśli konkretne funkcje kontrolowane przez klucz konfiguracji nie są używane, zostanie wygenerowana możliwości optymalizacji sugerująca wyłączenie klucza konfiguracji. Oto kilka przykładów kluczy konfiguracji: **Ilość efektywna**, **Planowanie budżetu**, **Projekt** i **Lista zatwierdzonych dostawców**.

### <a name="business-data-consistency-and-cleanup"></a>Spójność i oczyszczanie danych biznesowych

Jeśli dane główne nie są poprawne (na przykład jeśli masz przeliczenia jednostek miary na jednostki, które nie zostały zdefiniowane, lub przeliczenia obejmujące dzielenie przez 0 \[zero\]), zostanie wygenerowana możliwość optymalizacji sugerująca poprawienie danych. 

Jeśli masz zbyt wiele wpisów historii zadań przetwarzania wsadowego, nieaktualne towary, zamknięte wpisy towarów na stanie dla towarów magazynowych itd., albo jeśli te wpisy i towary są zbyt stare, zostaną wygenerowane możliwości optymalizacji sugerujące oczyszczenie danych. Utrzymując porządek wśród danych, można poprawić ogólną wydajność systemu.

### <a name="best-practices"></a>Najlepsze praktyki

Jeśli nie wykonujesz niektórych procesów biznesowych zgodnie z najlepszymi praktykami (na przykład jeśli dokonujesz wstępnego zamknięcia zapasów, zanim zapasy są faktycznie zamknięte, albo używasz zaplanowanego zadania wsadowego do przetwarzania wsadowego arkuszy księgi podrzędnej), możliwości optymalizacji informują o najlepszych praktykach i sugerują ich przestrzeganie.

## <a name="optimization-opportunities"></a>Możliwości optymalizacji

Aby wyświetlić możliwości optymalizacji wygenerowane podczas sprawdzania przestrzegania reguł optymalizacji, otwórz obszar roboczy **Doradca optymalizacji**.

W tym obszarze roboczym można wyświetlić dodatkowe informacje o możliwości, wybierając opcję **Więcej informacji**. Jeśli chcesz, aby system podjął działania i poprawił instalację, oczyścił dane itd., dzięki czemu nie musisz samodzielnie otwierać odpowiednich stron, wybierz opcję **Wykonaj akcję**.

Nie ma żadnego przepływu pracy dotyczącego możliwości optymalizacji. Gdy wybierzesz opcję **Wykonaj akcję** lub użyjesz ścieżki nawigacji podanej w oknie dialogowym **Więcej informacji**, możliwość optymalizacja zostanie usunięta z listy. Jeżeli działanie naprawcze nie rozwiąże całkowicie problemu, możliwość optymalizacji zostanie wygenerowana przy następnym sprawdzaniu przestrzegania reguły.

Jeśli możliwość optymalizacji nie ma zastosowania do Twojej roli, można wybrać opcję **Ukryj na mojej liście**. Nawet jeśli reguła stojąca za tą możliwością optymalizacji zostanie wyzwolona ponownie, nie zobaczysz tej możliwości na swojej liście.

Aby zdezaktywować weryfikację przestrzegania określonych reguł, wybierz możliwość optymalizacji wygenerowaną przez regułę, a następnie wybierz opcję **Dezaktywuj analizę**.

## <a name="see-also"></a>Informacje dodatkowe

[Tworzenie nowych reguł](./create-rules-optimization-advisor.md)

[Doradca optymalizacji w programie Dynamics 365 for Finance and Operations (film)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
