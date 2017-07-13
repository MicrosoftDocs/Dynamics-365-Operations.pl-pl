---
title: "Konfigurowanie zadania wykonywanego automatycznie w przepływie pracy"
description: "W tym temacie wyjaśniono sposób konfigurowania właściwości zadania wykonywanego automatycznie."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 66f1b8e03cc0da5d21fea9b3c795d8f4097c8cfc
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Konfigurowanie zadania wykonywanego automatycznie w przepływie pracy
<a id="configure-an-automated-task-in-a-workflow" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono sposób konfigurowania właściwości zadania wykonywanego automatycznie.

Aby skonfigurować zadanie wykonywane automatycznie, w edytorze przepływu pracy kliknij zadanie prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości zadania wykonywanego automatycznie.

## Nadawanie nazwy zadaniu
<a id="name-the-task" class="xliff"></a>
Wykonaj następujące kroki, aby wprowadzić nazwę zadania wykonywanego automatycznie.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Nazwa** wprowadź unikatową nazwę zadania.

## Określanie, kiedy są wysyłane powiadomienia
<a id="specify-when-notifications-are-sent" class="xliff"></a>
Można wysyłać powiadomienia do odpowiednich osób po ponownym uruchomieniu lub anulowaniu zadania wykonywanego automatycznie. Wykonaj następujące kroki, aby określić, kiedy i do kogo są one wysyłane.

1.  W lewym okienku kliknij opcję **Powiadomienia**.
2.  Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:
    -   **Wykonanie** — powiadomienia są wysyłane po wykonaniu zadania.
    -   **Anulowano** — powiadomienia są wysyłane po anulowaniu zadania.

3.  Zaznacz wiersz zdarzenia wybranego w kroku 2.
4.  Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.
5.  Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze. Podczas wyświetlania powiadomienia użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Wykonaj następujące czynności, aby wstawić symbol zastępczy:
    1.  W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.
    2.  Kliknij opcję **Wstaw symbol zastępczy**.
    3.  Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4.  Kliknij przycisk **Wstaw**.

6.  Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:
    1.  Kliknij opcję **Tłumaczenia**.
    2.  Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3.  Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.
    4.  W polu **Przetłumaczony tekst** wprowadź tekst.
    5.  Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.
    6.  Kliknij przycisk **Zamknij**.

7.  Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia. Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opcja</th>
    <th>Adresaci powiadomień</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td><ol>
    <li>Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy uczestniczący w bieżącym przepływie pracy</td>
    <td><ul>
    <li>Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Użytkownik</td>
    <td>Konkretny użytkownik programu Microsoft Dynamics 365 for Finance and Operations</td>
    <td><ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations. Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.





