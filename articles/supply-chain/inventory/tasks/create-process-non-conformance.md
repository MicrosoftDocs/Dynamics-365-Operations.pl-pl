---
title: Tworzenie i przetwarzanie niezgodności
description: Ten temat opisuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 032f5b712c2be5312524129cd25e655e778f5f44
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580871"
---
# <a name="create-and-process-nonconformances"></a>Tworzenie i przetwarzanie niezgodności

[!include [banner](../../includes/banner.md)]

Ten temat opisuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości. Zazwyczaj zarządzanie niezgodnościami jest wykonywane przez pracownika ds. kontroli jakości. Warunkiem wstępnym jest dostęp do zlecenia kontroli jakości. (Aby uzyskać informacje o tworzeniu zlecenia kontroli jakości, zobacz temat [Sprawdzanie jakości towarów](inspect-quality-goods.md)).

Aby użytkownik był w stanie przetworzyć zatwierdzenie niezgodności, musi być do niego przypisany pracownik w polu **Osoba** na stronie **Użytkownicy**. Ponadto, aby użytkownik mógł używać notatek do dokumentu, w polu **Włącz obsługę dokumentów** w jego opcjach użytkownika musi być ustawiona wartość *Tak*.

## <a name="create-a-nonconformance"></a>Tworzenie rekordu niezgodności

Aby utworzyć niezgodność, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Tworzenie niezgodności** w polu **Typ problemu** wybierz typ problemu, który został znaleziony w trakcie procesu inspekcji.
1. Kliknij przycisk **OK**.

## <a name="approve-or-reject-a-nonconformance"></a>Zatwierdzanie lub odrzucanie niezgodności

Aby zatwierdzić lub odrzucić niezgodność, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Korektę można dodać tylko do zatwierdzonych niezgodności.

1. W okienku akcji wybierz opcje **Funkcje \> Zatwierdź niezgodność**, aby zatwierdzić tę niezgodność, lub **Funkcje \> Odrzuć niezgodność**, aby ją odrzucić. Zatwierdzone niezgodności można skojarzyć z [powiązanymi operacjami](../quality-operations.md). W ten sposób można rejestrować pracę wykonaną w ramach obsługi niezgodności i przetwarzania obsługi korekt.
1. Zostanie wyświetlony monit o potwierdzenie wyboru. Wybierz przycisk **Tak**, aby kontynuować.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Dodawanie operacji i innych szczegółów do niezgodności

Po utworzeniu niezgodności można rozpocząć dodawanie powiązanych operacji i określenie dodatkowych informacji o tych operacjach. Powiązane operacje można dodać tylko do zatwierdzonych niezgodności.

Oprócz podstawowych informacji do operacji można dodawać następujące informacje:

- **Towary** — można utworzyć listę towarów zużywanych w celu wykonania korekty. Na przykład towary mogą być produktami wymaganymi do naprawy sprzętu lub substancjami wymaganymi do przeróbki gotowego produktu.
- **Opłaty związane z kontrolą jakości** — można utworzyć listę opłat, które zostały poniesione lub które są rozliczane w zewnętrznych źródłach.
- **Karta czasu pracy** — można utworzyć dziennik czasu, jaki każdy pracownik poświęca na operację.

Pozostałe ustawienia są opcjonalne. Koszt każdego towaru, opłaty związane z jakością i karta czasu pracy są sumowane i wyświetlane w operacji. Nie można bezpośrednio edytować pola **Koszt** w operacji.

### <a name="create-an-operation-for-a-nonconformance"></a>Tworzenie operacji dla niezgodności

Aby utworzyć operację dla niezgodności, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.

1. W okienku akcji wybierz pozycję **Powiązane operacje**.
1. Na stronie **Powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Operacja** — umożliwia wybranie kodu operacji, która zostanie wykonana dla niezgodności.
    - **Przyczyna** — służy do wprowadzania szczegółowego opisu objaśnienia powodu, dla którego operacja jest wymagana.
    - **Zamówienie sprzedaży** — jeśli wybrany kod operacji jest powiązany z typem zamówienia sprzedaży, należy wybrać zamówienie sprzedaży, z którym ma być powiązana operacja.
    - **Zamówienie zakupu** — jeśli wybrany kod operacji jest powiązany z typem zamówienia zakupu, należy wybrać zamówienie zakupu, z którym ma być powiązana operacja.

1. Zamknij strony.

### <a name="add-items-to-an-operation"></a>Dodawanie towarów do operacji

Aby dodać towary do operacji, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.

1. W okienku akcji wybierz pozycję **Powiązane operacje**.
1. Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać towary.
1. W okienku akcji kliknij pozycję **Towary**.
1. Na stronie **Powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Kod towaru** — umożliwia wybór produktu, który zostanie zużyty w ramach wybranej operacji.
    - **Ilość** — umożliwia wprowadzenie liczby towarów, które zostaną zużyte.

    > [!NOTE]
    > Koszt towaru można wyświetlić w polu **Koszt** na karcie **Ogólne**. Wyświetlany koszt pochodzi z kosztu ustawionego na stronie **Zwolniony produkt**. Nie można zaktualizować kosztu bezpośrednio na stronie **Towar operacji powiązanej**. Koszt wszystkich towarów dodawanych na stronie **Towary powiązanej operacji** jest automatycznie dodawany do pola **Koszt** na stronie **Operacje powiązane**.

1. Powtórz poprzedni krok dla każdego dodatkowego towaru, który musisz dodać.
1. Zamknij strony.

### <a name="add-quality-charges-to-an-operation"></a>Dodawanie opłat związanych z kontrolą jakości do operacji

Aby dodać opłaty związane z kontrolą jakości do operacji, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.

1. W okienku akcji wybierz pozycję **Powiązane operacje**.
1. Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać opłaty związane z kontrolą jakości.
1. W okienku akcji kliknij opcję **Opłaty związane z kontroli jakości**.
1. Na stronie **Opłaty za powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Kod opłat** — umożliwia wybór opłaty związanej z kontrolą jakości, która ma zostać dodana.
    - **Opis** – wprowadź szczegółowy opis opłaty.
    - **Wartość opłat** — umożliwia wprowadzanie kwoty do naliczenia.

1. Powtórz poprzedni krok dla każdej dodatkowej opłaty, którą musisz dodać.
1. Zamknij strony.

> [!NOTE]
> Kwota w polu **Wartość opłat** jest automatycznie sumowana dla wszystkich opłat związanych z kontrolą jakości i dodawana do innych kwot w polu **Koszt** na stronie **Operacje powiązane**.

### <a name="create-a-timesheet-on-an-operation"></a>Tworzenie karty czasu pracy dla operacji

Aby dodać kartę czasu pracy do operacji, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.

1. W okienku akcji wybierz pozycję **Powiązane operacje**.
1. Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać kartę czasu pracy.
1. W okienku akcji wybierz opcję **Karta czasu pracy**.
1. Na stronie **Karty czasu pracy powiązanej operacji** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Data** — umożliwia określenie daty zakończenia pracy. Domyślnie w tym polu jest wstawiona bieżąca data.
    - **Pracownik** — Pozwala wybrać pracownika, który wykonał pracę. Domyślnie w tym polu jest wstawiony pracownik przypisany do bieżącego użytkownika.
    - **Godziny operacji** — służy do wprowadzania liczby godzin przepracowanych przy wybranej operacji.
    - **Zafakturowane** — to pole wyboru należy zaznaczyć, jeśli faktura obciąża dostawcę lub odbiorcę.

    > [!NOTE]
    > Koszt można wyświetlić w polu **Koszt** na karcie **Ogólne**. Koszt jest obliczany przy użyciu stawki która jest zdefiniowana na stronie **Parametry zarządzania zapasami**.

1. Powtórz poprzedni krok dla każdego dodatkowego wiersza karty czasu pracy, który musisz dodać.
1. Zamknij strony.

> [!NOTE]
> Kwota w polu **Koszt** jest automatycznie sumowana dla wszystkich wierszy karty czasu pracy i dodawana do innych kwot w polu **Koszt** na stronie **Operacje powiązane**.

## <a name="add-a-correction-to-a-nonconformance"></a>Dodawanie korekty do niezgodności

Aby dodać korektę do niezgodności, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Korektę można dodać tylko do zatwierdzonych niezgodności.

1. W okienku akcji wybierz opcję **Korekty**.
1. Na stronie **Korekty**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Diagnostyka** — umożliwia wybranie typu diagnostyki identyfikującego typ korekty, która jest tworzona.
    - **Pracownik** — Umożliwia wybór osoby, która odpowiada za korektę.
    - **Priorytet korekty** — umożliwia wybór opcji wskazującej sposób ustalania priorytetów korekty (*Niski*, *Normalny* lub *Wysoki*).
    - **Data wnioskowania** — wprowadź datę wnioskowania o akcję korygującą.
    - **Data planowana** — umożliwia wprowadzenie oczekiwanej daty wykonania korekty.
    - **Rozwiązanie krótkoterminowe** — należy zaznaczyć to pole wyboru, jeśli akcja korekcyjna koryguje niezgodność tylko przez krótki czas.

1. Zamknij strony.

## <a name="mark-a-correction-as-completed"></a>Oznaczanie korekty jako zakończonej

Aby oznaczyć korektę niezgodności jako zakończoną, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.

    > [!NOTE]
    > Korektę można dodać tylko do zatwierdzonych niezgodności.

1. W okienku akcji wybierz opcję **Korekty**.
1. Na stronie **Korekty** w siatce zaznacz korektę, którą chcesz oznaczyć jako zakończoną.
1. W okienku akcji wybierz opcję **Oznacz jako ukończone**.
1. Zostanie wyświetlony monit o potwierdzenie wyboru. Wybierz przycisk **OK**, aby kontynuować. W polu **Data i godzina zakończenia** jest ustawiona bieżąca data i godzina, a pole wyboru **Zakończono** jest zaznaczone.
1. Zamknij stronę.

## <a name="reopen-a-completed-correction"></a>Ponowne otwieranie zakończonej korekty

Aby ponownie otworzyć zakończoną korektę, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.
1. Na liście zaznacz niezgodność, którą chcesz zaktualizować.
1. W okienku akcji wybierz opcję **Korekty**.
1. Na stronie **Korekty** w siatce zaznacz korektę, którą chcesz ponownie otworzyć.
1. W okienku akcji kliknij przycisk **Otwórz ponownie**.
1. Zostanie wyświetlony monit o potwierdzenie wyboru. Wybierz przycisk **OK**, aby kontynuować. Zawartość pola **Data i godzina ukończenia** zostanie wyczyszczona, a zaznaczenie pola wyboru **Zakończone** zostanie usunięte.
1. Zamknij stronę.

Teraz możesz dokonać dodatkowych edycji lub aktualizacji korekty. Po zakończeniu można ponownie oznaczyć korektę jako zakończoną.

## <a name="close-a-nonconformance"></a>Zamykanie rekordu niezgodności

Aby zamknąć niezgodność, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Wybierz zlecenie kontroli jakości w siatce.
1. W okienku akcji wybierz **Zapytania \> Niezgodności**.
1. Na stronie **Niezgodności** zaznacz w siatce docelową niezgodność.
1. W okienku akcji wybierz **Funkcje \> Zamknij niezgodność**.
1. Zostanie wyświetlony monit o potwierdzenie wyboru. Wybierz przycisk **Tak**, aby kontynuować.
1. Zamknij strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](../quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](../enable-quality-management.md)
- [Pracownicy odpowiedzialni za zatwierdzanie niezgodności](../quality-responsible-workers.md)
- [Strefy kwarantanny niezgodności](../quality-quarantine-zones.md)
- [Typy diagnostyki niezgodności](../quality-diagnostic-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](../quality-charges.md)
- [Operacje dotyczące niezgodności](../quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
