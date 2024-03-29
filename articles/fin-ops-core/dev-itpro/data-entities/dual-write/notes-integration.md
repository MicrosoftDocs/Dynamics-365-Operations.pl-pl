---
title: Integracja z notatkami
description: W tym artykule opisano integrację danych notatek w trybie zapisu podwójnego.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f09d455181b7929e25d5238949a0236ac60d457b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289025"
---
# <a name="note-integration"></a>Integracja z notatkami

[!include [banner](../../includes/banner.md)]



Podczas procesów biznesowych użytkownicy Microsoft Dynamics 365 często zbierają informacje o swoich klientach. Te informacje są rejestrowane jako działania i notatki. W tym artykule opisano integrację danych notatek w trybie zapisu podwójnego.

Informacje o odbiorcy można sklasyfikować w następujący sposób:

+ **Informacje przydatne w działaniu, które użytkownik Dynamics 365 obsługuje w imieniu klienta** – Na przykład Contoso (użytkownik Dynamics 365) prowadzi teleturniej. Jeden z klientów firmy Contoso (klient) chce wziąć udział w teleturnieju. Klient prosi pracownika firmy Contoso o zarezerwowanie dla niego miejsca w teleturnieju. Rezerwacja następuje w kalendarzu uczestnika zdarzenia firmy Contoso.
+ **Informacje przydatne dla użytkownika Dynamics 365** – Na przykład klient, który kupuje urządzenie Surface, wprowadza specjalne instrukcje, które wskazują, że urządzenie powinno zostać zapakowane na prezent przed dostawą. Te instrukcje to informacje umożliwiające wykonanie czynności, które powinien obsługiwać pracownik firmy Contoso odpowiedzialny za pakowanie.
+ **Informacje niepodlegające działaniu** – Na przykład klient odwiedza sklep Contoso i podczas rozmowy ze współpracownikiem wyraża zainteresowanie grami i akcesoriami do gier *Halo*. Pracownik sklepu odnotowuje te informacje. Następnie aparat rekomendacji produktów używa go do sporządzania rekomendacji dla odbiorcy.

Na ogół informacje dotyczące akcji są przechwytywane jako *działania* w aplikacjach finansowych i operacyjnych i aplikacjach dotyczących relacji z klientami. Na ogół informacje nie podlegające akcjom są przechwytywane jako *notatki* w aplikacjach finansowych i operacyjnych i jako *adnotacje* w aplikacjach dotyczących relacji z klientami.

> [!TIP]
> Chociaż notatki są przeznaczone dla informacji niepodlegających działaniu, aplikacje nie uniemożliwiają ich używania do przechowywania i obsługi informacji, które można wykonać, jeśli chcesz ich używać w ten sposób.

Firma Microsoft obecnie udostępnia funkcje integracji notatek. (Funkcjonalność integracji działań zostanie udostępniona później). Integracja notatek jest dostępna dla klientów, dostawców, zamówień sprzedaży i zamówień zakupu.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Utwórz notatkę w aplikacji angażującej klientów

Aby utworzyć notatkę w aplikacji angażującej klientów, a następnie zsynchronizować ją z aplikacjami finansowymi i operacyjnymi, wykonaj następujące kroki.

1. W aplikacji dotyczącej relacji z klientami otwórz rekord konta odbiorcy.
2. W okienku **Osi czasu** wybierz znak plus (**+**), a następnie wybierz pozycję **Notatka**, aby utworzyć notatkę.

    ![Utwórz notatkę w aplikacji angażującej klientów.](media/notes-ce-1.png)

3. Wprowadź tytuł i opis, a następnie wybierz opcję **Dodaj notatkę**.

    ![Wprowadzenie tytułu i opisu.](media/notes-ce-2.png)

    Nowa notatka zostanie dodana do osi czasu dla odbiorcy.

    ![Nowa notatka na osi czasu dla odbiorcy.](media/notes-ce-3.png)

4. Zaloguj się do aplikacji finansowych i operacyjnych i otwórz ten sam rekord odbiorcy. Zwróć uwagę, że przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu wskazuje, że rekord ma załącznik.

    ![Powiadomienie o załączniku.](media/notes-ce-4.png)

5. Wybierz przycisk **Załączniki**, aby otworzyć stronę **Załączniki**. Powinieneś znaleźć notatkę, którą utworzyłeś w aplikacji do obsługi klienta.

    ![Notatka z aplikacji angażującej klienta.](media/notes-ce-5.png)

Wszelkie aktualizacje notatki są synchronizowane między aplikacjami finansowymi i operacyjnymi a aplikacją do obsługi klienta.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Utwórz notatkę w aplikacjach finansowych i operacyjnych

Możesz również utworzyć notatkę w aplikacjach finansowych i operacyjnych, która zostanie zsynchronizowana z aplikacją do obsługi klienta.

Aby utworzyć notatkę w aplikacji angażującej klientów, a następnie zsynchronizować ją z aplikacjami finansowymi i operacyjnymi, wykonaj następujące kroki.

1. W aplikacjach finansowych i operacyjnych, na stronie **Załączniki** wybierz **Nowa** \> **Notatka**.

    ![Tworzenie notatki w aplikacjach finansowych i operacyjnych.](media/notes-fo-1.png)

2. Wprowadź tytuł i krótki zestaw instrukcji, a następnie wybierz polecenie **Zapisz**.

    ![Wprowadzanie tytułu i instrukcji.](media/notes-fo-2.png)

3. Zaktualizuj rekord w aplikacji angażującej klienta. Nowa notatka powinna znaleźć się na osi czasu.

    ![Nowa notatka na osi czasu w aplikacji do obsługi klienta.](media/notes-fo-3.png)

Notatkę można sklasyfikować jako wewnętrzną lub zewnętrzną.

- W aplikacjach finansowych i operacyjnych, na stronie **Załączniki** otwórz notatkę, a następnie w polu **Ograniczenie** wybierz pozycję **Wewnętrzna** lub **Zewnętrzna**.

    ![Pole ograniczenia.](media/notes-fo-4.png)

Można również utworzyć adres URL.

1. W aplikacjach finansowych i operacyjnych, na stronie **Załączniki** wybierz **Nowa** \> **URL**.
2. Wprowadź tytuł i adres URL.
3. W polu **Ograniczenie** wybierz opcję **Wewnętrzna** lub **Zewnętrzna**.

    ![Tworzenie URL w aplikacjach finansowych i operacyjnych.](media/notes-fo-5.png)

4. Wybierz opcję **Zapisz**.

    Ponieważ aplikacje angażujące klientów nie mają typu adresu URL, adres URL jest zintegrowany z podwójnym zapisem jako notatka.

    ![URL pojawiający się jako notatka w aplikacji budującej zaangażowanie klientów.](media/notes-ce-6.png)

> [!NOTE]
> Załączniki plików nie są obsługiwane.

## <a name="templates"></a>Szablony

Integracja notatek obejmuje zbiór map tabel, które współpracują podczas interakcji danych, jak pokazano w poniższej tabeli.

| Aplikacje finansowe i operacyjne | Aplikacja Customer Engagement | Opis |
|----------------------------|-------------------------|-------------|
| [Załączniki odbiorcy](mapping-reference.md#230) | Adnotacje | Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji specyficznych dla klienta (zarówno dla organizacji, jak i osób). |
| [Załączniki dokumentów dostawców](mapping-reference.md#231) | Adnotacje | Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji specyficznych dla dostawcy (zarówno dla organizacji, jak i osób). |
| [Załączniki dokumentu nagłówka zamówienia sprzedaży](mapping-reference.md#229) | Adnotacje | Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji dotyczących zamówienia sprzedaży. |
| [Załączniki dokumentu nagłówka zamówienia zakupu](mapping-reference.md#232) | Adnotacje | Firmy, które używają zwykłego tekstu i adresów URL do przechwytywania informacji dotyczących zamówienia zakupu. |

## <a name="limitations"></a>Ograniczenia

Po zainstalowaniu rozwiązania notatek nie można go odinstalować. 

Aby uzyskać więcej informacji, zobacz [Odniesienie do mapowania z podwójnym zapisem](mapping-reference.md).

