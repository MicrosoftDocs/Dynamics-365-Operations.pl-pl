---
title: Tworzenie zadania wsadowego
description: Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.
author: maertenm
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76c6c68f7effad0c40282b22ea2a6bf991862cf5
ms.sourcegitcommit: d7d997ad84623ad952672411c0eb6740972ae0b1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2021
ms.locfileid: "7864180"
---
# <a name="create-a-batch-job"></a>Tworzenie zadania wsadowego

[!include [banner](../../includes/banner.md)]

Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia. Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył. Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-the-batch-job"></a>Tworzenie zadania wsadowego
1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Zapytania > Zadania wsadowe**.
2. Wybierz pozycję **Nowy**.
3. W polu **Opis zadania** wprowadź opis zadania wsadowego.
4. W polu **Zaplanowana data/godzina rozpoczęcia** wprowadź datę i godzinę uruchomienia zadania wsadowego.
5. Wybierz opcję **Zapisz**.

## <a name="create-a-recurrence"></a>Tworzenie cyklu
1. W Panelu akcji wybierz **Zadanie wsadowe**.
2. Ustaw **Cykl**. Te opcje służą do wprowadzania zakresu i wzorca cyklu.  
3. Kliknij przycisk **OK**.

## <a name="add-alerts"></a>Dodawanie alertów
1. W Panelu akcji wybierz **Zadanie wsadowe**.
2. Wybierz **Alerty**. Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu. Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.   
3. Kliknij przycisk **OK**.

## <a name="add-a-task-to-a-batch-job"></a>Dodawanie zadanie do zadania wsadowego
1.  Na stronie **Zadania wsadowe** wybierz pozycję **Wyświetl zadania**.
2.  Naciśnij klawisze **Ctrl+N**, aby utworzyć zadanie.
3.  Wprowadź opis zadania wsadowego.
4.  W polu **Konta firm** wybierz firmową bazę danych, w której będzie uruchamiane zadanie.
5.  W polu **Nazwa klasy** wybierz proces, który zadanie powinno uruchomić. 
6.  W razie potrzeby wybierz grupę partii dla zadania.

    Zadania klienta muszą być przypisane do grupy zadań wsadowych. Są one automatycznie przypisywane do domyślnej grupy partii (zwanej również pustą grupą partii).

7.  Naciśnij klawisze **Ctrl+S**, aby zapisać zadanie.
8.  Aby uzależnić wybrane zadanie od innego zadania w zadaniu, zaznacz siatkę **Ma warunki**, a następnie wykonaj następujące czynności dla każdego warunku, który chcesz zdefiniować:

    1. Naciśnij klawisze **Ctrl+N**, aby utworzyć warunek.
    2. Wybierz identyfikator zadania dla zadania nadrzędnego.
    3. Wybierz stan, jaki musi osiągnąć zadanie nadrzędne, aby mogło zostać uruchomione zadanie zależne.
    4. Naciśnij klawisze **Ctrl+S**, aby zapisać warunek.

    Jeśli określisz wiele warunków i *wszystkie* one muszą być spełnione, aby mogło zostać uruchomione zadanie zależne, wybierz typ warunku **Wszystko**. Jeśli zadanie zależne mogło zostać uruchomione w przypadku spełnienia *wszystkich* warunków, wybierz typ warunku **Wszystko**.

9.  Wybierz sposób obsługi niepowodzeń zadań. Aby niepowodzenie wykonania określonego zadania było ignorowane, na karcie **Ogólne** zaznacz opcję **Ignoruj niepowodzenie zadania** dla tego zadania. Jeśli ta opcja jest wybrana, niepowodzenie wykonania zadania nie powoduje niepowodzenia wykonania zadania. Możesz również użyć pola **Minimalna liczba prób**, aby określić liczbę prób ponownego wykonania zadania, zanim zostanie ono uznane za niepomyślne. Zaleca się, aby w polu **Maksymalna liczba ponownych prób** nie ustawić wartości większej niż **5**.

    Aby uzyskać więcej informacji o ponownych próbach przetwarzania wsadowego, zobacz temat [Włączanie ponownych prób przetwarzania wsadowego](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Dostosuj status zadania wsadowego
1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Wybierz właściwe zadanie wsadowe.
3. W Panelu akcji wybierz **Zadanie wsadowe > Funkcje > Zmień status**.
4. Wybierz właściwy status:
    - **Wstrzymane**: Ustaw status zadania wsadowego jako **wstrzymane**, żeby zostało usunięte z planu zadań wsadowych. Jest to odpowiednik *stop*.
    - **Oczekujące**: Ustaw status zadania wsadowego jako **oczekujące**, żeby zostało wpisane na listę zadań oczekujących na dodanie do planu zadań wsadowych. Jest to odpowiednik *iść*.
5. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
