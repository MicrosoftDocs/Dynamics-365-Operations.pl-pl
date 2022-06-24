---
title: Konfigurowanie i zarządzanie rejestrowaniem bazy danych
description: Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8faf0be5f094f18b75f2263fa622c9b7f3983274
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899771"
---
# <a name="configure-and-manage-database-logging"></a>Konfigurowanie i zarządzanie rejestrowaniem bazy danych


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych. W tym artykule opisano sposób wykonywania następujących czynności:

- Zarządzanie zabezpieczeniami i wydajnością dla rejestrowania w bazie danych
- Konfigurowanie rejestrowania bazy danych
- Oczyszczanie dzienników bazy danych

## <a name="overview-of-database-logging"></a>Omówienie rejestrowania w bazie danych

Można śledzić zmiany rejestrowania w bazie danych w tabelach i polach w Dynamics 365 Human Resources. Te zmiany obejmują wstawianie, aktualizowanie lub usuwanie. Rejestrowanie w bazie danych zapisuje rekord zmian w tabelach lub polach w tabeli dziennika bazy danych.

Do zastosowań biznesowych w rejestrowaniu bazy danych należą:

- Tworzenie rekordu inspekcji zmian w konkretnych tabelach zawierających poufne informacje.
- Śledzenie pojedynczych transakcji. Rejestrowanie w bazie danych nie jest przeznaczone do śledzenia zautomatyzowanych transakcji uruchamianych w zadaniach wsadowych.

## <a name="security-for-database-logging"></a>Zabezpieczenia dotyczące rejestrowania w bazie danych

Dzienniki bazy danych mogą zawierać dane poufne. Umożliwia ograniczenie dostępu, aby obejmował tylko role zabezpieczeń wymagające dostępu do danych dziennika.

## <a name="database-logging-and-performance"></a>Rejestrowanie i wydajność bazy danych

Podczas gdy wartość jest cenna od perspektywy biznesowej, rejestrowanie w bazie danych może być kosztowne w użyciu i zarządzaniu zasobami. Wpływ rejestrowania bazy danych na wydajność obejmuje:

- Tabela dziennika bazy danych może szybko rosnąć i powodować zwiększenie rozmiaru bazy danych. Wzrost zależy od ilości zarejestrowanych danych, które mają zostać zachowane. Domyślnie tabela dziennika bazy danych obsługuje tylko 30 dni danych dziennika. 

- Rejestrowanie bazy danych może niekorzystnie wpłynąć na długotrwałe procesy, takie jak długotrwałe importowanie danych.

### <a name="best-practices"></a>Najlepsze praktyki

Aby poprawić wydajność, ogranicz wpisy dziennika, wybierając określone pola do zapisania zamiast całych tabel. W celu zapewnienia ogólnej wydajności rejestrowanie w bazie danych jest ograniczone do 20 tabel.

> [!NOTE]
> Można rejestrować tylko aktualizacje dla poszczególnych pól.

## <a name="set-up-database-logging"></a>Konfigurowanie rejestrowania bazy danych

Aby skonfigurować rejestrowanie bazy danych, można skorzystać z kreatora **Rejestracji zmian w bazie danych**. Kreator stanowi elastyczny sposób konfigurowania rejestrowania tabel lub pól.

1. Przejdź do **Administrowanie systemem > Łącza > Baza danych > Ustawienia dziennika bazy danych**. Wybierz opcję **Nowy**, aby uruchomić kreatora **Rejestracji zmian w bazie danych**.
2. Wybierz pozycję **Następny**. 
3. Na stronie **Tabele i pola** kreatora wybierz tabele i pola, w których chcesz włączyć rejestrowanie bazy danych, i wybierz przycisk **Dalej**.

   > [!Note]
   > Rejestrowanie bazy danych nie jest dostępne we wszystkich tabelach w bazie danych Zasoby ludzkie. Wybranie opcji **Pokaż wszystkie tabele** pod listą spowoduje rozwinięcie listy tabel i pól w celu pokazania wszystkich tabel baz danych, dla których jest dostępne rejestrowanie bazy danych, ale będzie to podzestaw pełnej listy tabel bazy danych.

4. Na stronie **Typy zmian** w kreatorze wybierz operacje na danych, dla których chcesz śledzić zmiany poszczególnych tabel i pól, a następnie wybierz przycisk **Dalej**. Opis operacji dotyczących danych dostępnych do rejestrowania znajduje się w poniższej tabeli.
5. Na stronie **Zakończ** przejrzyj zmiany, które zostaną wprowadzone, i wybierz przycisk **Zakończ**.

| Operacja | opis |
| -- | -- |
| Śledź nowe transakcje | Utwórz dziennik dla nowych rekordów, które są tworzone w tabeli. |
| Aktualizowanie | Umożliwia tworzenie dziennika aktualizacji rekordów tabeli lub aktualizacji pojedynczych pól w tabeli. Jeśli użytkownik wybierze opcję rejestrować aktualizacje tabeli, po każdym zaktualizowaniu dowolnego pola rekordu w tabeli tworzony jest rekord dziennika. Jeśli użytkownik wybierze opcję rejestrować aktualizacje określonych pól, rekord dziennika jest tworzony tylko podczas aktualizacji tych pól rekordów tabel. |
| Usuwanie | Utwórz dziennik dla rekordów usuniętych z tabeli. |
| Klucz zmiany nazwy | Utwórz rekord dziennika po zmianie nazwy klucza tabeli. |


## <a name="clean-up-database-logs"></a>Oczyszczanie dzienników bazy danych

Można usunąć wszystkie dzienniki bazy danych lub ich część, korzystając z następujących opcji:

- Umożliwia wybór wszystkich dzienników dla określonej tabeli.
- Wybierz określone typy dziennika bazy danych.
- Umożliwia wybranie daty i godziny utworzenia dziennika.

Aby skonfigurować czyszczenie dziennika bazy danych, wykonaj następujące kroki: 

1. Przejdź do **Administrowanie systemem > Łącza > Baza danych > Dziennik bazy danych**. Wybierz opcję **Oczyszczanie dziennika**.
2. W sekcji **Rekordy do uwzględnienia** wybierz **Filtr**.
3. Wybierz metodę, która będzie używana do wybierania dzienników do usunięcia. Wprowadź jedną z poniższych opcji:

   - ID tabeli
   - Typ dziennika
   - Data i godzina utworzenia

4. Karta **Czyszczenie dziennika bazy danych** umożliwia określenie, kiedy ma być wykonywane zadanie oczyszczania dziennika. Domyślnie dzienniki bazy danych są dostępne przez 30 dni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
