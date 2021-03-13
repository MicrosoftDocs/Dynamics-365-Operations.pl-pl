---
title: Konfigurowanie i zarządzanie rejestrowaniem bazy danych
description: Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50346cc495fe08f49137dba59dbcbb3f7f838c7b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129286"
---
# <a name="configure-and-manage-database-logging"></a>Konfigurowanie i zarządzanie rejestrowaniem bazy danych

Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych. W tym temacie opisano sposób:

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
2. Wykonaj czynności w kreatorze.

## <a name="clean-up-database-logs"></a>Oczyszczanie dzienników bazy danych

Można usunąć wszystkie dzienniki bazy danych lub ich część, korzystając z następujących opcji:

- Umożliwia wybór wszystkich dzienników dla określonej tabeli.
- Wybierz określone typy dziennika bazy danych.
- Umożliwia wybranie daty i godziny utworzenia dziennika.

Aby skonfigurować czyszczenie dziennika bazy danych, wykonaj następujące kroki: 

1. Przejdź do **Administrowanie systemem > Łącza > Baza danych > Dziennik bazy danych**. Wybierz opcję **Oczyszczanie dziennika**.

2. Wybierz metodę wybierania dzienników do usunięcia, wprowadzając jedną z następujących opcji:

   - ID tabeli
   - Typ dziennika
   - Data i godzina utworzenia

3. Karta **Czyszczenie dziennika bazy danych** umożliwia określenie, kiedy ma być wykonywane zadanie oczyszczania dziennika. Domyślnie dzienniki bazy danych są dostępne przez 30 dni.
