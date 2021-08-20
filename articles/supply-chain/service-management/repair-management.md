---
title: Zarządzanie naprawami
description: Warto systematycznie grupować problemy, tak aby ułatwić podpowiadanie rozwiązań, które wcześniej okazały się trafne.
author: ShylaThompson
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa739685791596fe1a3dce3abff344b21b8d7f6dd5cefc525c7e749a75138a9b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774688"
---
# <a name="repair-management"></a>Zarządzanie naprawami       

[!include [banner](../includes/banner.md)]


W celu zarządzania naprawami można regularnie grupować problemy. Ułatwi to sugerowanie rozwiązań, które wcześniej okazały się trafne.

Definiuje się ustawienia objawów, diagnozy i rozwiązania. Wszystkie te parametry można później zastosować, gdy otrzymasz podobny przedmiot do naprawy. Można także skonfigurować etapy naprawy, aby ułatwić śledzenie postępów w procesie naprawiania.

## <a name="setting-up-repair-management"></a>Konfigurowanie zarządzania naprawami

Następujące formularze ustawień służą do wprowadzania informacji, które będą służyć do określania objawów, diagnozy i sposobów rozwiązania dla napraw.

- **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Warunki**.
- **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary objawów**.
-  **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Obszary diagnoz**.
- **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Rozwiązania**.
- **Zarządzanie serwisem** \> **Ustawienia** \> **Naprawa** \> **Etapy napraw**.

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

1.  Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz zlecenie serwisowe z przedmiotem serwisu wymagającym naprawienia.

3.  Wybierz opcje **Naprawa** \> **Wiersze naprawy**, aby otworzyć formularz **Wiersze naprawy**.

4.  Wybierz pozycję **Nowy**, aby utworzyć nowy wiersz.

5.  Wybierz przedmiot serwisu. Można wybrać dowolny przedmiot serwisu, dla którego skonfigurowano relację obiektu do zlecenia serwisowego.

6.  Wybierz te predefiniowane objawy, diagnozy lub wartości wykonania, które są odpowiednie w wypadku danego wiersza naprawy, a następnie w razie potrzeby wybierz kartę **Notatka**, aby utworzyć notatkę do wiersza naprawy.

7.  Wybierz **Zapisz**, aby zapisać nowy wiersz naprawy. Pole **Data i godzina utworzenia** na karcie **Ogólne** w formularzu **Wiersze naprawy** zostanie zaktualizowane o godzinę zapisania.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Śledzenie postępu i rozwiązywanie problemu

Dla wiersza naprawy można definiować etapy naprawy, aby śledzić postęp naprawy.

Po rozwiązaniu problemu można zamknąć wiersz naprawy. Ustaw etap naprawy z włączoną właściwością **Zakończono**. Jako czas zakończenia w wierszu zostanie zarejestrowana aktualna data i godzina.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Zamykanie wiersza naprawy dla rozwiązanej sprawy

1.  Otwórz formularz **Wiersze naprawy**. Postępując zgodnie z przedstawioną wcześniej procedurą, utwórz wiersz naprawy.

2.  Wybierz wiersz naprawy ze sprawą naprawy, która ma zostać zamknięta.

3.  W polu **Etap naprawy** wybierz etap z włączoną właściwością **Zakończono**.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]