---
title: Zarządzanie naprawami
description: Warto systematycznie grupować problemy, tak aby ułatwić podpowiadanie rozwiązań, które wcześniej okazały się trafne.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d45732ff35069a64b37b6c53d9e22adf9a9a46d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975615"
---
# <a name="repair-management"></a>Zarządzanie naprawami       

[!include [banner](../includes/banner.md)]


W celu zarządzania naprawami można regularnie grupować problemy. Ułatwi to sugerowanie rozwiązań, które wcześniej okazały się trafne.

Definiuje się ustawienia objawów, diagnozy i rozwiązania. Wszystkie te parametry można później zastosować, gdy otrzymasz podobny przedmiot do naprawy. Można także skonfigurować etapy naprawy, aby ułatwić śledzenie postępów w procesie naprawiania.

## <a name="setting-up-repair-management"></a>Konfigurowanie zarządzania naprawami

Następujące formularze ustawień służą do wprowadzania informacji, które będą służyć do określania objawów, diagnozy i sposobów rozwiązania dla napraw.

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Warunki**.

2.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary objawów**.

3.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary diagnoz**.

4.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Rozwiązania**.

5.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Etapy napraw**.

## <a name="symptoms-and-conditions"></a>Objawy i warunki

Objawy to charakterystyka problemu przedstawiona przez klienta. Objawy obejmują spostrzeżenia klienta sugerujące konieczność naprawy.

Można skonfigurować obszary objawów, kody objawów i warunki. Obszar objawów dotyczy obszaru nieprawidłowego funkcjonowania, a kod objawu dotyczy objawu nieprawidłowego funkcjonowania. Warunek opisuje sytuację lub środowisko, jakie istnieje w momencie występowania problemu.

**Przykład**

Do naprawy dostarczono komputer, ponieważ dysk twardy przestaje działać po dłuższym okresie pracy. Awaria dysku twardego powoduje że błąd niebieskiego ekranu. Serwisant, który odbiera komputer, wprowadza następujące objawy i warunki:

1.  Obszarem objawów jest dysk twardy

2.  Kodem objawu jest błąd niebieskiego ekranu

3.  Warunek mówi, że dysk twardy przestaje działać po dłuższym okresie pracy

## <a name="diagnosis-and-resolutions"></a>Diagnostyka i rozwiązania

Pola diagnostyki i rozwiązania stanowią raporty z przebiegu naprawy. Są to etapy, przez które przechodził personel techniczny, starając się zdiagnozować problem.

Obszar diagnoz określa operację, którą należy wykonać, aby rozwiązać problem. Kod diagnozy określa sposób postępowania przy obsłudze problemu, a rozwiązaniem może być informacja o naprawieniu towaru, wymianie elementu lub wycofaniu zlecenia przez klienta. Na przykład jeśli naprawiono komputer, to obszarem diagnozy może być informacja „uszkodzona część”, kodem diagnozy może być „zainstalowano nową kartę graficzną”, a rozwiązaniem byłoby stwierdzenie „wymieniono”.

## <a name="repair-stages"></a>Etapy napraw

Etapy napraw odnoszą się do postępu prac w procesie naprawy. Etap napraw ma parametr zamykający **Zakończono**, który oznacza, że wiersz naprawy został ukończony oraz zarejestrowano datę i godzinę zakończenia.

## <a name="applying-repair-management"></a>Wdrożenie zarządzania naprawą

Aby zastosować zasady zarządzania naprawą w kontekście jakiegoś towaru, towar ten musi być skonfigurowany w taki sposób, aby istniała relacja przedmiotu serwisu ze zleceniem serwisowym. Dopiero wtedy z poziomu zlecenia serwisowego można utworzyć wiersz naprawy z informacjami dotyczącymi bieżącego przypadku. W wierszu reperacji jest definiowany przedmiot serwisu podlegający reperacji, a także informacje o objawach, diagnozie i wykonaniu. Można też sporządzić notatkę dla wiersza naprawy.

Wiersze naprawy można utworzyć dla każdego etapu procesu naprawy.

## <a name="create-a-repair-line-on-a-service-order"></a>Tworzenie wiersza naprawy do zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz zlecenie serwisowe z przedmiotem serwisu wymagającym naprawienia.

3.  Kliknij kolejno opcje **Naprawa** \> **Wiersze naprawy**, aby otworzyć formularz **Wiersze naprawy**.

4.  Naciśnij klawisze CTRL+N, aby utworzyć nowy wiersz.

5.  Wybierz przedmiot serwisu. Można wybrać dowolny przedmiot serwisu, dla którego skonfigurowano relację obiektu do zlecenia serwisowego.

6.  Wybierz te predefiniowane objawy, diagnozy lub wartości wykonania, które są odpowiednie w wypadku danego wiersza naprawy, a następnie w razie potrzeby kliknij kartę **Notatka**, aby utworzyć notatkę do wiersza naprawy.

7.  Naciśnij klawisze CTRL+S, aby zapisać nowy wiersz naprawy. Pole **Data i godzina utworzenia** na karcie **Ogólne** w formularzu **Wiersze naprawy** zostanie zaktualizowane o godzinę zapisania.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Śledzenie postępu i rozwiązywanie problemu

Dla wiersza naprawy można definiować etapy naprawy, aby śledzić postęp naprawy.

Po rozwiązaniu problemu można zamknąć wiersz naprawy. Ustaw etap naprawy z włączoną właściwością **Zakończono**. Jako czas zakończenia w wierszu zostanie zarejestrowana aktualna data i godzina.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Zamykanie wiersza naprawy dla rozwiązanej sprawy

1.  Otwórz formularz **Wiersze naprawy**. Postępując zgodnie z przedstawioną wcześniej procedurą, utwórz wiersz naprawy.

2.  Wybierz wiersz naprawy ze sprawą naprawy, która ma zostać zamknięta.

3.  W polu **Etap naprawy** wybierz etap z włączoną właściwością **Zakończono**.

  


