---
title: Parametry magazynu dla przetwarzania grupy czynności
description: W tym artykule opisano sposób konfigurowania parametrów magazynu dla przetwarzania grupy czynności. Można użyć przetwarzania grupy czynności do pogrupowania pracy pobierania dla wielu zamówień w jedną grupę czynności.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2a64cba837faf84f3e8470a9831d1641213a5cc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909620"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Parametry magazynu dla przetwarzania grupy czynności

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania parametrów magazynu dla przetwarzania grupy czynności. Można użyć przetwarzania grupy czynności do pogrupowania pracy pobierania dla wielu zamówień w jedną grupę czynności.

Aby użyć przetwarzania grupy czynności, na stronie **Parametry zarządzania magazynem** określ następujące elementy:

- Jeśli możesz, przetwarzaj grupy czynności przy użyciu zadania wsadowego.
- W przypadku zbierania informacji w pliku dziennika podczas przetwarzania grupy czynności.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Konfigurowanie parametrów magazynu dla przetwarzania grupy czynności

W celu ustawienia parametrów dla przetwarzania grupy czynności, należy wykonać następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Parametry zarządzania magazynem**.

1. Na skróconej karcie **przetwarzania grupy czynności** należy wprowadzić następujące ustawienia:

    - **Grupa partii przetwarzania grupy czynności** - Wybierz grupę zadań wsadowych do użycia podczas przetwarzania grup czynności przy użyciu zadań wsadowych. Grupa zadań wsadowych określa serwer, na którym będą uruchamiane zadania wsadowe.
    - **Przetwarzaj wsadowe zadania przetwarzania wsadowego** — określ, czy chcesz, aby zadania wsadowe były automatycznie przetwarzane. Aby korzystać z przetwarzania równoległego, musisz ustawić wartość *Tak*. Zadanie wsadowe można ustawić na stronie **Przetwarzanie grupy czynności**. (Zobacz także notatkę na końcu tej listy)
    - **Utwórz dziennik postępu grupy czynności** — określ, czy system powinien generować rekord dziennika przy każdej alokacji dla pozycji i gdy jej wymiary zaczynają i kończą się. Ten dziennik należy włączyć tylko wtedy, gdy jest potrzebny, na przykład podczas testowania lub rozwiązywania problemów. - aby uzyskać więcej informacji, zobacz [Alokacja grupy czynności](wave-allocation-method.md).
    - **Utwórz dziennik historii przetwarzania grupy czynności** — umożliwia określenie, czy informacje o grupy czynności mają być zapisywane automatycznie w pliku dziennika po przetworzeniu grupy czynności, w tym podczas równoległego przetwarzania alokacji oczekujących. Zazwyczaj tę opcję należy włączyć tylko podczas rozwiązywania problemów, ponieważ powoduje to dodanie dodatkowych kosztów ogólnych. Aby wyświetlić dziennik, przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Dziennik historii przetwarzania grup czynności**. Aby uzyskać więcej informacji o przetwarzaniu grupy czynności, zobacz temat [Tworzenie i przetwarzanie grup czynności](wave-processing.md).
    - **Utwórz dziennik historii tworzenia kontenerów** — określ, czy po przetworzeniu grupy czynności mają być automatycznie zapisywane informacje dotyczące tworzenia kontenerów dla grupy czynności w pliku dziennika. Aby wyświetlić dziennik, przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Historia konteneryzacji**.
    - **Oczekiwanie na blokadę (ms)** - Wprowadź czas w milisekundach, przez który krok alokacji zaczeka na zasób systemowy zablokowany przez inny krok alokacji. Po przekroczeniu tego czasu grupa czynności nie jest przetwarzana i zostanie wyświetlony komunikat o błędzie.

1. Na skróconej karcie **Zwolnienie do magazynu** należy wprowadzić następujące ustawienie:

    - **Błąd w przypadku niepowodzenia przetwarzania wsadowego** — określ, czy ma być generowany błąd w przypadku niepowodzenia zadania wsadowego zwalniania do magazynu. Jeśli ta opcja jest włączona, zadania nieudane zakończą się stanem *Błąd*. Jeśli ta opcja jest wyłączona, zadania nieudane zakończą się stanem *Zakończono*.

> [!NOTE]
> W szablonie grup czynności, który jest używany do przetwarzania grupy czynności można określić ustawienia, które automatyzują przetwarzanie grupy czynności. W przypadku ustawienia harmonogramu dla zadania wsadowego, należy dostosować czas z ustawieniami automatyzacji w szablonie grupy czynności. Aby uzyskać więcej informacji, zobacz temat [Tworzenie szablonu grupy czynności](wave-templates.md).
>
> Jeśli używasz *Zarządzanie transportem* i *Zaawansowane zarządzanie magazynem*, możesz określić, czy skonsolidować ładunki podczas przetwarzania grupy czynności. Na przykład jest to przydatne przy jednoczesnym wysyłaniu kilku małych ładunków. Aby skonsolidować ładunki podczas przetwarzania grupy czynności, na karcie **Ładunki** zaznacz pole wyboru **Konsoliduj ładunki podczas przetwarzania grupy czynności**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Konfigurowanie rezerwacji pełnej lub częściowej dla grup czynności produkcji

W przypadku zamówień sprzedaży i zamówień Kanban zapasy muszą być zarezerwowane przed zwolnieniem zamówienia do magazynu. W przeciwnym razie towary lub wiersze alokacji nie mogą zostać przetworzone w grupie czynności. Zlecenia produkcyjne są jednak nieco bardziej elastyczne. W przypadku zleceń produkcyjnych należy określić:

- Określ, czy wszystkie materiały muszą zostać zarezerwowane przed zwolnieniem zamówienia do magazynu. Jeśli zostanie wybrana ta opcja, należy ręcznie powtórzyć zwolnienia do procesu magazynowego, gdy dodatkowe materiały stają się dostępne. Na przykład jest to przydatne w przypadku materiałów, których produkcję należy uruchomić, i można poczekać, aż materiały dodatkowe stają się dostępne.
- Określ, czy wszystkie materiały muszą zostać zarezerwowane przed zwolnieniem zamówienia do magazynu.

Aby wymagać pełnej rezerwacji lub zezwolić na częściową rezerwację, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Kontrola produkcji** \> **Ustawienia** \> **Wybierz kolejno opcje Kontrola produkcji**.
1. Na karcie **Ogólne** w polu **Zwolnij do magazynu** wybierz ustawienie domyślne.
