---
title: Konfigurowanie właściwości przepływu pracy
description: W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.
author: sericks007
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d745389b37b899760ea32ae75c5cb80d9139be2d
ms.sourcegitcommit: 1852f08f015acd106f4cefd03fa07985dc009123
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3199443"
---
# <a name="configure-workflow-properties"></a>Konfigurowanie właściwości przepływu pracy

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania różnych właściwości przepływu pracy.

Aby skonfigurować właściwości przepływu pracy, otwórz przepływ pracy w edytorze przepływu pracy. Kliknij w obszarze roboczym edytora przepływu pracy, a następnie kliknij przycisk **Właściwości**, aby otworzyć stronę **Właściwości**. Można użyć poniższych procedur, aby skonfigurować różne właściwości przepływu pracy.

## <a name="name-the-workflow"></a>Nadawanie nazwy przepływowi pracy

Należy wykonać następujące kroki, aby wprowadzić nazwę przepływu pracy.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Nazwa** wprowadź unikatową nazwę przepływu pracy. Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, można nazwać przepływy **Zapotrzebowania na zakup — Dania** lub **Zapotrzebowania na zakup — Hiszpania**.

## <a name="specify-the-workflow-owner"></a>Określanie właściciela przepływu pracy

Właściciel przepływu pracy jest osobą, która zarządza przepływem pracy i obsługuje go. Aby określić właściciela przepływu pracy, należy wykonać następujące kroki.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Na liście **Właściciel** zaznacz nazwę osoby, która będzie zarządzać przepływem pracy.

## <a name="select-an-email-template"></a>Wybór szablonu wiadomości e-mail

Wykonaj następujące kroki, aby wybrać szablon wiadomości e-mail, który będzie używany do generowania komunikatów powiadomień dotyczących przepływu pracy.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Na liście **Szablon wiadomości e-mail dla powiadomień o przepływie pracy** zaznacz szablon.

## <a name="enter-instructions-for-users"></a>Wprowadzanie instrukcji dla użytkowników

Istnieje możliwość udostępniania instrukcji użytkownikom, którzy będą przesyłać dokumenty do przetwarzania i zatwierdzania. Ci użytkownicy są również zwani *inicjatorami*. Na przykład tworzysz przepływ pracy zapotrzebowania na zakup i wprowadzasz instrukcje. Te instrukcje mogą być wyświetlane przez użytkowników wprowadzających zapotrzebowania na zakup na stronie **Zapotrzebowania na zakup**. Aby wyświetlić instrukcje, inicjator klika ikonę na pasku komunikatów przepływu pracy. Aby wprowadzić instrukcje dla użytkowników, należy wykonać następujące kroki.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Instrukcje przesyłania** wprowadź instrukcje.
3. Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze. Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Aby wstawić symbol zastępczy, wykonaj następujące czynności:

    1. Kliknij w polu **Instrukcje przesyłania**, aby określić miejsce wyświetlania symbolu zastępczego.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.

4. Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze. Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 3.
    6. Kliknij przycisk **Zamknij**.

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a>Określ, kiedy ten przepływ pracy jest używany w warunkach aktywacji

Można utworzyć wiele przepływów pracy opartych na tym samym typie przepływu pracy. Jeśli istnieje wiele przepływów pracy opartych na tym samym typie, trzeba określić warunki używania poszczególnych przepływów pracy w warunkach aktywacji. Jeśli warunki aktywacji nie są spełnione, zostanie użyty domyślny przepływ pracy. Podobnie, jeśli dla danego typu przepływu pracy zdefiniowano tylko jedną konfigurację przepływu pracy, konfiguracja przepływu pracy będzie używana niezależnie od warunków aktywacji.

Na przykład można utworzyć przepływ pracy zapotrzebowania na zakup dla każdego kraju lub regionu, w którym działa firma, na przykład Zapotrzebowania na zakup — Dania lub Zapotrzebowania na zakup — Hiszpania, z następującymi warunkami:

- Zapotrzebowania na zakup — Dania jest używany, gdy krajem/regionem jest DK.
- Zapotrzebowania na zakup — Hiszpania jest używany, gdy krajem/regionem jest ES.

Aby określić, kiedy ma być używany konfigurowany przepływ pracy, należy wykonać następujące kroki.

1. W lewym okienku kliknij opcję **Aktywacja**.
2. Zaznacz pole wyboru **Ustaw warunki uruchamiania tego przepływu pracy**.
3. Kliknij opcję **Dodaj warunek**.
4. Służy do wprowadzania warunku.
5. Wprowadź wszelkie wymagane dodatkowe warunki.
6. Aby sprawdzić, czy wprowadzone warunki są poprawnie ustawione, wykonaj następujące czynności:

    1. Kliknij przycisk **Test**.
    2. Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.
    3. Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki. Na przykład jeśli tworzysz przepływ pracy zapotrzebowania na zakup dla Hiszpanii, obszar **Sprawdź poprawność warunku** na stronie zawiera listę zapotrzebowań na zakup. Kliknięcie przycisku **Test** spowoduje uruchomienie systemowego szacowania wybranego zapotrzebowania na zakup w celu sprawdzenia, czy krajem/regionem jest ES.
    4. Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.

## <a name="specify-when-notifications-are-sent"></a>Określanie, kiedy są wysyłane powiadomienia

Podczas przesyłania dokumentu do przetwarzania tworzone jest wystąpienie przepływu pracy. Można wysyłać powiadomienia do użytkowników, gdy wystąpienia przepływu pracy oparte na przepływie pracy są uruchamiane, kończone, przerywane lub zatrzymane z powodu błędu. Aby określić, kiedy są wysyłane powiadomienia, należy wykonać następujące kroki.

1. W lewym okienku kliknij opcję **Powiadomienia**.
2. Zaznacz pole wyboru dla każdego zdarzenia, które powinno uruchamiać powiadomienia:

    - **Rozpoczęte** — wysyłanie powiadomień po uruchomieniu wystąpienia przepływu pracy.
    - **Zatrzymane** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu błędu.
    - **Ukończono** — wysyłanie powiadomień po zakończeniu wystąpienia przepływu pracy.
    - **Nieodwracalne** — wysyłanie powiadomień, gdy wystąpienie przepływu pracy zostało zatrzymane z powodu nieodwracalnego błędu.
    - **Przerwane** — wysyłanie powiadomień po przerwaniu wystąpienia przepływu pracy.

3. Zaznacz wiersz zdarzenia wybranego w kroku 2.
4. Na karcie **Tekst powiadomienia** wprowadź tekst powiadomienia.
5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze. Podczas wyświetlania tekstu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi. Aby wstawić symbol zastępczy, wykonaj następujące czynności:

    1. Kliknij w polu, aby określić miejsce wyświetlania symbolu zastępczego.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.
    5. Popularnym dołączanym elementem zastępczym **Tekst powiadomienia** jest „Ostatnie uwagi: %Workflow.Last note%”, który pokazuje wszystkie komentarze z poprzedniego kroku.

6. Aby dodać tłumaczenia tekstu, wykonaj następujące kroki:

    1. Kliknij opcję **Tłumaczenia**.
    2. Na wyświetlonej stronie kliknij przycisk **Dodaj**.
    3. Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.
    4. W polu **Przetłumaczony tekst** wprowadź tekst.
    5. Aby spersonalizować tekst, możesz wstawić symbole zastępcze. Aby uzyskać instrukcje dotyczące sposobu wprowadzania symbolu zastępczego, zobacz krok 5.
    6. Kliknij przycisk **Zamknij**.

7. Na karcie **Adresat** użyj poniższych opcji do określenia, kto ma otrzymywać powiadomienia.

    <table>
    <thead>
    <tr>
    <th>Opcja</th>
    <th>Powiadomienia są tym użytkownikom</th>
    <th>Aby wysyłać powiadomienia, należy wykonać następujące czynności</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Uczestnik</td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td>
    <ol>
    <li>Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Uczestnik</strong>.</li>
    <li>Na karcie <strong>Oparte na</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Użytkownik przepływu pracy</td>
    <td>Użytkownicy będący uczestnikami tego przepływu pracy</td>
    <td>
    <ol>
    <li>Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik przepływu pracy</strong>.</li>
    <li>Na karcie <strong>Użytkownik przepływu pracy</strong> na liście <strong>Użytkownik przepływu pracy</strong> wybierz uczestnika w tym przepływie pracy.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Użytkownik</td>
    <td>Określeni użytkownicy</td>
    <td>
    <ol>
    <li>Na karcie <strong>Odbiorcy</strong> kliknij przycisk <strong>Użytkownik</strong>.</li>
    <li>Na karcie <strong>Użytkownik</strong> lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników. Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Wprowadzanie komentarzy dotyczących zmian zastosowanych w przepływie pracy

Aby wprowadzić komentarze dotyczące zmian zastosowanych w przepływie pracy, należy wykonać następujące kroki.

1. W lewym okienku kliknij opcję **Uwagi**.
2. W polu **Wprowadź komentarze dotyczące przepływu pracy** wprowadź komentarze.
3. Przejrzyj wprowadzone komentarze. Po dodaniu komentarzy nie można ich modyfikować.
4. Kliknij przycisk **Dodaj**, aby dodać komentarze do obszaru **Historia komentarzy**.
