---
title: Konfigurowanie procesów zatwierdzania w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości procesu zatwierdzania.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b09d09464eae932bf9caf4f2ea38cbbb3b4f0162
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190219"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Konfigurowanie procesów zatwierdzania w przepływie pracy

[!include [banner](../includes/banner.md)]

Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości procesu zatwierdzania.

Aby skonfigurować proces zatwierdzania, w edytorze przepływu pracy kliknij element zatwierdzania prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarty formularz **Właściwości**.

## <a name="name-the-approval-process"></a>Nadawanie nazwy procesowi zatwierdzania

Aby wprowadzić nazwę procesu zatwierdzania, należy wykonać poniższe kroki.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Nazwa** wprowadź unikatową nazwę procesu zatwierdzania.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Określanie, kiedy system automatycznie wykonuje operację na dokumencie

System można skonfigurować do automatycznego wykonywania operacji na dokumencie, gdy są spełnione określone warunki. Na przykład system może zatwierdzać raporty o wydatkach, których suma kwot jest mniejsza niż 100 USD. Wykonaj następujące kroki, aby określić, kiedy system podejmuje akcję wobec dokumentu.

1. W lewym okienku kliknij opcję **Akcje automatyczne**.
2. Zaznacz pole wyboru **Włącz akcje automatyczne**.
3. Kliknij opcję **Dodaj warunek**.
4. Służy do wprowadzania warunku.
5. W razie potrzeby wprowadź dodatkowe warunki.
6. Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:

    1. Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.
    2. Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.
    3. Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki.
    4. Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.

7. Z listy **Akcja automatycznego ukończenia** wybierz akcję, jaką ma podjąć system wobec dokumentu.

## <a name="specify-when-notifications-are-sent"></a>Określanie, kiedy są wysyłane powiadomienia

Możliwe jest wysyłanie do odpowiednich osób powiadomień w przypadku zatwierdzenia, odrzucenia, delegowania lub eskalowania dokumentu albo żądania jego modyfikacji. Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.

1. W lewym okienku kliknij opcję **Powiadomienia**.
2. Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:

    - **Delegowanie** — gdy dokument został przypisany innemu użytkownikowi do zatwierdzenia.
    - **Eskalowanie** — kiedy przypisany użytkownik nie podjął działań wobec dokumentu w wyznaczonym czasie.
    - **Zatwierdzanie** — po zatwierdzeniu dokumentu.
    - **Odrzucanie** — po odrzuceniu dokumentu.
    - **Żądanie zmiany** — gdy przypisany użytkownik zażądał wprowadzenia zmiany w przesłanym mu dokumencie.

3. Zaznacz wiersz zdarzenia wybranego w kroku 2.
4. Kliknij kartę **Tekst powiadomienia**.
5. W polu tekstowym wprowadź treść powiadomienia.
6. Aby spersonalizować tekst, można wstawić symbole zastępcze, które będą zastępowane odpowiednimi danymi podczas wyświetlania użytkownikom. Aby wstawić symbol zastępczy, wykonaj następujące czynności:

    1. Kliknij pole tekstowe w miejscu, gdzie ma się pojawiać symbol zastępczy.
    2. Kliknij opcję **Wstaw symbol zastępczy**.
    3. Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.
    4. Kliknij przycisk **Wstaw**.

7. Aby dodać tłumaczenia powiadomienia, kliknij opcję **Tłumaczenia**. W wyświetlonym formularzu wykonaj następujące czynności:

    1. Kliknij przycisk **Dodaj**.
    2. Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.
    3. W polu tekstowym **Przetłumaczony tekst** wprowadź tekst.
    4. Aby spersonalizować tekst, wstaw symbole zastępcze.
    5. Kliknij przycisk **Zamknij**.

8. Kliknij kartę **Adresat**.
9. Określ, komu zostaną wysłane powiadomienia. Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 10.

    <table>
    <thead>
    <tr>
    <th>Opcja</th>
    <th>Adresaci powiadomień</th>
    <th>Dodatkowe kroki</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><strong>Uczestnik</strong></td>
    <td>Użytkownicy, którzy są przypisani do określonej grupy lub roli</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Uczestnik</strong> kliknij kartę <strong>Oparte na roli</strong>.</li>
    <li>Na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub rolę, do której mają być wysyłane powiadomienia.</li>
    <li>Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Użytkownik przepływu pracy</strong></td>
    <td>Użytkownicy uczestniczący w bieżącym przepływie pracy</td>
    <td>
    <ol>
    <li>Po wybraniu opcji <strong>Użytkownik przepływu pracy</strong> kliknij kartę <strong>Użytkownik przepływu pracy</strong>.</li>
    <li>Na liście <strong>Użytkownik przepływu pracy</strong> zaznacz użytkownika, który uczestniczy w przepływie pracy.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Użytkownik</strong></td>
    <td>Określeni użytkownicy</td>
    <td>
    <ol>
    <li>Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</li>
    <li>Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Powtórz kroki od 3 do 9 dla każdego zdarzenia wybranego w kroku 2.

## <a name="specify-a-final-approver"></a> Określanie ostatecznej osoby zatwierdzającej

Można wyznaczyć osobę ostatecznie zatwierdzającą dla scenariuszy, gdzie osobą zatwierdzającą jest użytkownik, który przesłał dokument do zatwierdzenia. Aby określić ostateczną osobę zatwierdzającą, wykonaj następujące kroki.

1. W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2. Zaznacz pole wyboru **Użyj ostatecznej osoby zatwierdzającej**.
3. Wybierz z listy użytkownika, który ma być osobą ostatecznie zatwierdzającą.

## <a name="set-a-time-limit"></a>Ustawianie limitu czasu

Jeśli proces zatwierdzania musi zostać ukończony w określonym czasie, wykonaj następujące kroki.

> [!NOTE]
> Opcje wybrane w tych krokach zastąpią opcje wybrane w obszarach **Przypisanie** i **Eskalacja** w poszczególnych krokach zatwierdzania.

1. W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2. Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu** **pracy**.
3. W polu **Czas trwania** określ, do kiedy proces zatwierdzania ma zostać ukończony. Umożliwia wybranie jednej z następujących opcji:

    - **Godziny** — Wprowadź liczbę godzin, w ciągu których należy ukończyć proces zatwierdzania. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Dni** — Wprowadź liczbę dni, w ciągu których należy ukończyć proces zatwierdzania. Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.
    - **Tygodnie** — Wprowadź liczbę tygodni, w ciągu których należy ukończyć proces zatwierdzania.
    - **Miesiące** — Wybierz dzień i tydzień, do kiedy należy ukończyć proces zatwierdzania. Może to być na przykład piątek trzeciego tygodnia w miesiącu.
    - **Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy ukończyć proces zatwierdzania. Może to być na przykład piątek trzeciego tygodnia grudnia.

4. W przypadku przekroczenia tego limitu czasu system wykona operację na dokumencie. Na liście **Akcja** zaznacz akcję, jaką ma podjąć system.

## <a name="specify-which-actions-are-available-to-the-user"></a>Określanie akcji dostępnych użytkownikowi

Gdy dokument zostanie przypisany do użytkownika, aby go zatwierdził, użytkownik musi zareagować na dokument. Wykonaj następujące kroki, aby określić, które akcje użytkownik może wykonywać na przesłanym dokumencie.

1. W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.
2. Zaznacz pole wyboru **Zatwierdzanie**, jeśli użytkownik może zatwierdzić dokument.
3. Zaznacz pole wyboru **Odrzucanie**, jeśli użytkownik może odrzucić dokument.
4. Zaznacz pole wyboru **Żądanie zmiany**, jeśli użytkownik może wnioskować o zmiany w dokumencie.
5. Zaznacz pole wyboru **Delegowanie**, jeśli użytkownik może przypisać dokument innemu użytkownikowi do zatwierdzenia.

> [!NOTE]
> Pole wyboru **Włącz wykonywanie akcji z listy zadań w module Enterprise Portal** zostało wycofane.

## <a name="configure-the-approval-steps"></a> Konfigurowanie kroków zatwierdzania

Proces zatwierdzania składa się z kroków zatwierdzania. Należy wykonać poniższą procedurę, aby dodać kroki procesu zatwierdzania i je skonfigurować.

1. W edytorze przepływu pracy kliknij dwukrotnie procesu zatwierdzania. Edytor przepływu pracy wyświetli etapy procesu zatwierdzania.
2. Aby dodać krok zatwierdzania, przeciągnij go z obszaru **Elementy przepływu pracy** na kanwę.
3. Aby skonfigurować krok zatwierdzania, zobacz [Konfigurowanie kroku zatwierdzania](configure-approval-step-workflow.md).
