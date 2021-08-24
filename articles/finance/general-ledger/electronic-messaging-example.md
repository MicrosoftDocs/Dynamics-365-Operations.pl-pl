---
title: Konfigurowanie i uruchamianie przetwarzania do wywołania prostego formatu eksportowania ER to wygenerować raportu programu Excel
description: W tym temacie przedstawiono przykład, który pokazuje, jak skonfigurować i używać wiadomości elektronicznych.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a5fd466c98e0855f7a33929eeee42b9147d26ba19780b4ae7c8eb895ac27ea5e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737684"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Konfigurowanie i uruchamianie przetwarzania do wywołania prostego formatu eksportowania ER to wygenerować raportu programu Excel

[!include [banner](../includes/banner.md)]

Po utworzeniu formatu ER, przyporządkowaniu go do źródeł danych i wykonaniu go, można uruchomić go za pomocą obszaru roboczego **Raportowanie elektroniczne** . Po wygenerowaniu raportu możesz go zapisać lokalnie.

Aby kontrolować następujące aspekty procesu raportowania, skonfiguruj przetwarzanie wiadomości elektronicznych:

- Informacje dziennika o tym, kto wygenerował raport.
- Informacje dziennika o tym, kiedy został wygenerowany raport.
- Zapisz raporty, które zostały wygenerowane za poprzednie okresy.

Ta sekcja zawiera przykład, który pokazuje, jak można skonfigurować wiadomości elektroniczne do generowania raportu, który jest oparty na formacie eksportowania ER do programu Microsoft Excel. Jeśli chcesz postępować zgodnie z tym przykładem, format eksportowania ER dla programu Excel musi być już utworzony, zamapowany na źródła danych i ukończony. Ponadto numer sekwencji musi być skonfigurowany w wiadomościach elektronicznych.

Kiedy ustawiasz przetwarzanie, warto najpierw zdefiniować akcje przetwarzania i stany, które zostaną skonfigurowane. Poniższa ilustracja przedstawia przetwarzanie w tym przykładzie.

![Schemat przetwarzania](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Tworzenie stanów wiadomości

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Stany wiadomości**.
2. Utwórz następujące stany wiadomości:

    - Nowy
    - Przygotowane
    - Wygenerowane

    ![Stany wiadomości](media/message-statuses.png)

3. W wierszu stanu **nowy** zaznacz pole **Zezwalaj na usuwanie**, aby umożliwić użytkownikom usuwanie wiadomości o tym stanie.

## <a name="create-additional-fields"></a>Utwórz dodatkowe pola

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Dodatkowe pola**.
2. Dodaj dodatkowe pole i jego wartości.
3. Ustaw opcję **Edycja użytkownika** jako **tak**, aby umożliwić użytkownikom edycję tego pola.

![Dodatkowe pola](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Tworzenie akcji przetwarzania wiadomości

W tym przykładzie utworzysz następujące akcje przetwarzania wiadomości:

- **Utwórz komunikat**
- **Aktualizuj do stanu Przygotowane**
- **Generuj raport**
- **Aktualizuj do stanu początkowego** (opcjonalnie)

Wykonaj poniższe czynności, aby utworzyć akcje.

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Akcje przetwarzania wiadomości**.
2. Utwórz akcję o nazwie **Utwórz wiadomość**. Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Utwórz wiadomość**.
3. Tworzenie akcji o nazwie **Aktualizuj do stanu Przygotowane** i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **początkowe stany** w polu **stan wiadomości** zaznacz **nowa**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Przygotowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

4. Utwórz akcję o nazwie **Generuj raport** i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Eksport raportowania elektronicznego**. W polu **mapowanie formatu** wybierz format eksportu ER. Dostępne opcje to **Excel**, **XML**, **JSON**, **Tekst** i **Inne**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Przygotowane**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Wygenerowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

    ![Akcja Generowanie raportu](media/generate-report-action.png)

5. Opcjonalnie: aby umożliwić użytkownikom kilkakrotne ponowne generowanie raportu, utwórz działanie o nazwie **aktualizacji do stanu początkowego** i ustawić następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Wygenerowane**.
    - Na karcie skróconej **Stany wyników** dodaj osobny wiersz dla każdego z dwóch stanów wiadomości (**Przygotowana** i **Nowa**). W przypadku obu wierszy należy ustawić pole **typu odpowiedzi** jako **Wykonano pomyślnie**.

## <a name="electronic-message-processing"></a>Przetwarzanie wiadomości elektronicznych

W tym przykładzie wszystkie akcje powinny być ustawione tak, żeby działały oddzielnie. Zakłada się, że każda akcja zostanie zainicjowana przez użytkownika.

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Przetwarzanie wiadomości elektronicznych**.
2. Dodaj rekord do przetwarzania i dodaj wszystkie uprzednio zdefiniowane akcje oraz dodatkowe pole.
3. Opcjonalnie: Na skróconej karcie **ról zabezpieczeń** zdefiniuj role zabezpieczeń do przetwarzania, aby ograniczyć dostęp do określonego raportowania.
4. Przejdź do menu **Podatek** \> **Zapytania i raporty** \> **Wiadomości elektroniczne** \> **Wiadomości elektroniczne**.
5. Wybierz **Nowa**, aby utworzyć wiadomość. W tym momencie można dodać daty i opis. Można też zaktualizować wartość dodatkowego pola, jeśli jest to konieczne.

    ![Tworzenie wiadomości elektronicznej](media/create-electronic-message.png)

    Siatka na skróconej karcie **dziennik akcji** jest automatycznie wypełniany na podstawie dziennika wszystkich akcji wykonanych w odniesieniu do wiadomości.

    Można teraz usunąć lub zaktualizować stan wiadomości. 

6. Aby zaktualizować stan wiadomości, zaznacz **aktualizacja stanu**. W polu **Nowy stan** wybierz opcję **Przygotowana**, a następnie wybierz **OK**.

    ![Aktualizowanie stanu wiadomości](media/update-status.png)

    Stan komunikatu zostanie zaktualizowany do stanu **Przygotowane**.

7. Wygeneruj raport, wybierając **Generuj raport**.

    Raport zostanie wygenerowany, a stan wiadomości i dziennik akcji zostaną zaktualizowane.

8. Aby obejrzeć wygenerowany raport, wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
