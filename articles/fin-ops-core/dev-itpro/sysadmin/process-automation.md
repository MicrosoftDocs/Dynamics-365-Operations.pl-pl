---
title: Automatyzacja procesu
description: Ten artykuł zawiera szczegółowe informacje dotyczące sposobu, w jaki funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: f13392fd6610735f8c539d42b62cf71cece71fba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898617"
---
# <a name="process-automation"></a>Automatyzacja procesu

[!include[banner](../includes/banner.md)]

Funkcja Automatyzacji procesów umożliwia proste planowanie procesów, które będą wykonywane przez serwer przetwarzania wsadowego. Zaktualizowany widok kalendarza pracy zaplanowanej umożliwia użytkownikom końcowym przeglądanie i podejmowanie działań dot. planowanej i zakończonej pracy.

## <a name="administration"></a>Administracja

Strona Administracji centralnej dla wszystkich automatyzacji procesów znajduje się w module administrowania systemem w menu **Ustawienia**. Na tej stronie będzie wyświetlona lista wszystkich zautomatyzowanych procesów (seria) skonfigurowanych w systemie. Umożliwi to również dodawanie nowych automatyzacji procesów bezpośrednio z poziomu tej strony. Po skonfigurowaniu serii można zarządzać każdą z serii z tej listy. Można wybrać opcję edycji całej serii, usunąć ją, wyświetlić wszystkie wystąpienia w widoku listy lub wyłączyć serię, jeśli chcesz wstrzymać pracę według harmonogramu przez pewien czas. 

Żadne procesy wyłączone w module Zarządzanie funkcjami nie będą widoczne, gdy funkcja jest wyłączona. Ponadto aparat planowania automatyzacji procesów nie będzie planować wystąpień ani procesów wykonywanych w tle dla wyłączonej funkcji. Ponowne włączenie tej funkcji spowoduje natychmiastowe uruchomienie wszystkich zaplanowanych w przeszłości wystąpień lub procesów w tle. Działanie aparatu planowania automatyzacji procesów zależy od systemowego zadania wsadowego **Sondowanie automatyzacji procesów**. Zadania nie należy w żadnym momencie zmieniać ani modyfikować. 

## <a name="calendar-view"></a>Widok kalendarza

Jedną z głównych zalet automatyzacji procesu jest możliwość wyświetlania pracy według harmonogramu w prostym widoku kalendarzowym.  Ten widok umożliwia oglądanie pracy w danym tygodniu. Ten widok będzie dostępny po prawej stronie strony **Automatyzacji procesów**. Zostanie ona wypełniona pracą według harmonogramu dla wybranej serii. 

[![Kalendarz automatyzacji procesu.](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Zmiany wystąpienia

Każde wystąpienie może zostać zmodyfikowane bez wpływu na inne wystąpienia zdefiniowane przez serie, w których powstały. Wystąpienia zaplanowanej pracy można edytować w widoku kalendarza, wybierając przycisk **Widok/Edycja** i wybierając polecenie **Wystąpienie**. Ta strona umożliwia to dostęp do wszystkich ustawień początkowo wyświetlanych w Kreatorze ustawień serii i umożliwia dokonywanie jednorazowej zmiany w wybranym wystąpieniu. Wystąpienie pracy zaplanowanej można również wyłączyć, zaznaczając przycisk **Wyłącz** w widoku Kalendarz.

## <a name="developer-documentation"></a>Dokumentacja dewelopera

Struktura automatyzacji procesów umożliwia programistom rozszerzenie struktury automatyzacji procesów. W dokumentacji [Struktura automatyzacji procesów](../process-automation/process-automation-framework.md) znajdują się informacje dotyczące sposobu tworzenia niestandardowych procesów, które trzeba uruchomić przez serwer przetwarzania wsadowego zaplanowanego za pomocą Kreatora automatyzacji procesów i automatycznie wyświetlanych w widoku Kalendarz.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
