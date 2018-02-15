---
title: "Typy arkuszy księgi"
description: "W tym artykule opisano typy arkuszy, które można skonfigurować jako arkusze finansowe. Strona **Nazwy arkuszy** służy do konfigurowania arkuszy, których można używać w całym programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: ccd1b9056f8c18de1b2ef706f70f53bac6cc43a1
ms.contentlocale: pl-pl
ms.lasthandoff: 01/19/2018

---

# <a name="ledger-journal-types"></a>Typy arkuszy księgi

[!include[banner](../includes/banner.md)]


W tym artykule opisano typy arkuszy, które można skonfigurować jako arkusze finansowe. Strona **Nazwy arkuszy** służy do konfigurowania arkuszy, których można używać w całym programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

| Typ arkusza                      | Cel                       | Ta strona służy do wprowadzania transakcji                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Alokacja                        | Utwórz transakcje alokacji w arkuszu alokacji. Zanim będzie można utworzyć arkusz alokacji, trzeba utworzyć regułę alokacji na stronie **Reguła alokacji księgi**.      | Przetwarzanie żądania alokacji             |
| Zatwierdzenie                          | Zaksięguj zatwierdzone faktury dostawcy na odpowiednich kontach księgowych.  | Arkusz zatwierdzania faktur                                       |
| Cofnięcie czeku bankowego               | Wycofywanie zaksięgowanego czeku. Aby używać tego typu arkusza, wybierz opcję **Cofnij płatność w ramach procesu przeglądu** na stronie **Parametry modułu Zarządzanie gotówką i bankami**.   | Cofnięcia czeków, Cofnięcie płatności                   |
| Anulowanie dokumentu wpłaty bankowej    | Anuluj dokument wpłaty. Aby używać tego typu arkusza, wybierz opcję **Anuluj dokumenty wpłaty w ramach procesu przeglądu** na stronie **Parametry modułu Zarządzanie gotówką i bankami**.   | Anulaty bankowych dowodów wpłaty            |
| Budżet                            | Przetwarzaj asygnaty budżetu. Aby używać tego typu arkusza, zaznacz opcję **Włączanie asygnaty budżetu** na stronie **Parametry księgi głównej**. Zapisy arkusza budżetu będą zawierać informację oparte na kontach księgowych, które są zdefiniowane na stronie **Definicje księgowania**.                                                        |                                                                |
| Akceptacja weksla przez odbiorcę  | Utwórz transakcje przyjęcia odbiorców dla weksli.             | Arkusz wystawiania weksli, Arkusz ponownego wystawiania weksli |
| Przelew bankowy odbiorcy          | Utwórz pliku przekazu weksla, który może zostać przesłany do banku w Twojej organizacji. Aby użyć tego typu arkusza, wyczyść opcję **Automatyczne rozliczanie** dla na stronie **Parametry modułu Rozrachunki** **z dostawcami**.            | Przekaz                                                     |
| Weksel wystawiony odbiorcy    | Utwórz transakcje weksli wystawionych odbiorcy. Aby użyć tego typu arkusza, wyczyść opcję **Automatyczne tworzenie i księgowanie arkusza wystawiania podczas księgowania faktur** na stronie **Metody płatności — Odbiorcy**.   | Arkusz wystawiania weksli                                  |
| Płatność od odbiorcy                  | Utwórz transakcje płatności odbiorcy.                             | Arkusz płatności             |
| Oprotestowany weksel odbiorcy | Utwórz transakcje oprotestowanego weksla odbiorcy.                    | Arkusz protestowania weksli                               |
| Ponownie wystawiony weksel odbiorcy  | Utwórz transakcje weksli wystawionych ponownego odbiorcy.                     | Arkusz ponownego wystawiania weksli                                |
| Rozliczony weksel odbiorcy  | Utwórz transakcje rozliczonego weksla odbiorcy.                       | Arkusz rozliczania weksli                                |
| Dziennie                             | Utwórz transakcje dzienne w arkuszu finansowym.                          | Arkusze finansowe                                                |
| Eliminacja                       | Utwórz transakcje eliminacji w arkuszu eliminacji. Aby użyć tego typu arkusza, zaznacz opcje **Użyj na potrzeby procesu eliminacji finansowej** i **Użyj na potrzeby procesu konsolidacji finansowej** na stronie **Firmy**. Zanim będzie można użyć tego typu arkusza, trzeba utworzyć regułę eliminacji księgi na stronie **Reguła eliminacji księgi**. | Eliminacja                                                    |
| Budżet środków trwałych                | Utwórz wpisy do rejestru budżetu środków trwałych.                                                                                                                                                                                                                                                                                                                 | Budżet środków trwałych                                             |
| Rejestr faktur                  | Zarejestruj podstawowe informacje dotyczące faktur dostawcy.                                                                                                                                                                                                                                                                                                           | Rejestr faktur                                               |
| Rozchód dla listy płac              | Wydaj płatności oparte na sprawozdaniach płatności listy płac. Nie można ręcznie wprowadzić transakcji w tym arkuszu. Należy wygenerować sprawozdania o wynagrodzeniach, a następnie przesłać te sprawozdania do dokonania płatności.                                                                                                                                                              |                                                                |
| Okresowe                          | Utwórz transakcje okresowe dla arkusza okresowego.                                                                                                                                                                                                                                                                                                      | Arkusze okresowe                                              |
| Księgowanie środków trwałych                 | Zaksięguj transakcje środków trwałych.                                                                                                                                                                                                                                                                                                                              | Środki trwałe                                                   |
| Projekt — Wydatki                | Utwórz transakcje wypływu/wypłaty w projekcie.                                                                                                                                                                                                                                                                                                                        | Wydatek                                                        |
| Transakcje statystyczne            | Utwórz transakcje statystyczne.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Przelew bankowy dostawcy            | Utwórz plik przekazu skryptu dłużnego, który może zostać przesłany do banku Twojej organizacji.                                                                                                                                                                                                                                                                      | Arkusz przekazów                                             |
| Wypłaty dla dostawców               | Utwórz transakcje rozchodów dostawcy.                                                                                                                                                                                                                                                                                                                    | Arkusz płatności                                                |
| Skrypt dłużny wystawiony dostawcy       | Pobieranie skryptów dłużnych dostawcy jako metoda płatności. Aby użyć tego typu arkusza, wyczyść opcję **Automatyczne tworzenie i księgowanie arkusza wystawiania podczas księgowania faktur** na stronie **Metody płatności — Dostawcy**.                                                                                                                                          | Arkusz wystawiania skryptów dłużnych                                   |
| Pula faktur od dostawcy z wyłączeniem księgowań | Utwórz transakcje faktur dostawcy, które nie zostały jeszcze zaksięgowane na tymczasowym koncie przybycia.                                                                                                                                                                                                                                                             | Szczegóły puli faktur od dostawcy bez księgowania                  |
| Pula faktur dostawcy               | Utwórz transakcje puli faktur dostawcy.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Rejestracja faktury dostawcy          | Zaksięguj faktury od dostawcy znajdujące się w arkuszu.                                                                                                                                                                                                                                                                                                                 | Arkusz faktur                                                |
| Skrypt dłużny ponownie wystawiony dostawcy     | Ponownie wystaw skrypt dłużny, który wcześniej został uznany przez bank Twojej organizacji.                                                                                                                                                                                                                                                                      | Arkusz ponownego wystawiania skryptów dłużnych                                 |
| Rozliczenie skryptu dłużnego dostawcy     | Utwórz transakcje rozliczania skryptu dłużnego dostawcy.                                                                                                                                                                                                                                                                                                          | Arkusz rozliczania skryptów dłużnych                                 |






