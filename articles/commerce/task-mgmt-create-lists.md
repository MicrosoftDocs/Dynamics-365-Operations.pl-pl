---
title: Tworzenie list zadań i dodawanie zadań
description: W tym artykule opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b81f27f79362516f8a25766c1f663a7691ebb42a
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746167"
---
# <a name="create-task-lists-and-add-tasks"></a>Tworzenie list zadań i dodawanie zadań

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.

*Zadanie* definiuje określony element pracy lub akcję, którą ktoś musi zakończyć w dniu lub przed określonym terminem płatności. W Dynamics 365 Commerce zadanie może zawierać szczegółowe instrukcje i informacje o osobie kontaktowej. Może również zawierać łącza do operacji związanych z kopiami zapasowymi, operacje punktu sprzedaży (POS) lub stron witryny w celu zwiększenia produktywności i zapewnienia kontekstu potrzebnego właścicielowi zadania w celu efektywnego wykonania zadania.

*Lista zadań* to zbiór zadań, które należy wykonać w ramach procesu biznesowego. Na przykład może to być lista zadań, którą nowy pracownik musi zakończyć w celu przechodzenia do systemu, listy zadań dla kasjerów, którzy pracują wieczorem lub z listy zadań, które muszą zostać wypełnione, aby przygotować sklep do nadchodzącego sezonu wakacyjnego. W Commerce, każda lista zadań z datą docelową może zostać przypisana do dowolnej liczby sklepów lub pracowników i może zostać skonfigurowana do ponownego wystąpienia.

Zarówno kierownicy, jak i pracownicy mogą tworzyć listy zadań w biurze zaplecza w Commerce, a następnie przypisywać je do zbioru sklepów.

## <a name="create-a-task-list"></a>Utwórz nową listę zadań

Przed rozpoczęciem procesu tworzenia listy zadań upewnij się, że zostały ukończone konfiguracje w artykule [Konfigurowanie zarządzania zadaniami](task-mgmt-configure.md). Aby utworzyć listę zadań, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.
1. Wybierz **Nowy**, a następnie wprowadź wartości w polach **Nazwa**, **Opis** i **Właściciel**.
1. Wybierz opcję **Zapisz**.

## <a name="add-tasks-to-a-task-list"></a>Dodawanie zadań do listy zadań

Aby dodać zadanie do listy zadań, wykonaj następujące kroki.
 
1. Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Nowe**, aby dodać zadanie.
1. W nowym oknie dialogowym **Utwórz nowe zadanie**, w polu **Nazwa** wprowadź unikatową nazwę zadania.
1. W polu **Przesunięcie danych należnych od daty docelowej** wprowadź dodatnią lub ujemną wartość całkowitą. Na przykład wprowadź **-2**, jeśli zadanie ma zostać wykonane dwa dni przed datą ukończenia listy zadań.
1. W polu **Uwagi** wprowadź szczegółowe instrukcje.
1. W polu **Osoba kontaktowa** wprowadź nazwisko eksperta w danej dziedzinie, z którym właściciel zadania może się skontaktować, jeśli potrzebuje pomocy.
1. W polu **Łącze zadania** wprowadź łącze na podstawie charakteru zadania.

> [!TIP]
> Chociaż można skorzystać z pola **Przypisane do**, aby przydzielić zadania komuś podczas tworzenia listy zadań, zaleca się uniknięcie przypisywania zadań podczas tworzenia listy zadań. Zamiast tego należy przypisywać zadania po utworzeniu wystąpienia listy dla poszczególnych sklepów.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Korzystanie z łączy zadań w celu poprawy produktywności pracowników

Commerce umożliwia połączenie zadań z określonymi operacjami w punkcie sprzedaży, takich jak raport sprzedaży, wyświetlanie materiałów wideo szkoleniowych w trybie online dla nowych pracowników lub wykonywanie operacji biura zaplecza. Ta funkcja ułatwia właścicielom zadań uzyskiwanie informacji potrzebnych do wydajnego wykonania zadania.

Aby dodać łącza do zadań podczas tworzenia zadania, należy wykonać następujące kroki.

1. Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Edytuj**.
1. W oknie dialogowym **Edytuj zadanie** w polu **Łącze zadania** wybierz jedną lub więcej z następujących opcji:

    - Wybierz **Element menu**, aby skonfigurować operację zaplecza (np. „zestawy produktów”).
    - Wybierz **Operację punktu sprzedaży**, aby skonfigurować operację punktu sprzedaży, taką jak „raporty o sprzedaży”.
    - Wybierz opcję **adres URL**, aby skonfigurować bezwzględny adres URL.

Na poniższej ilustracji przedstawiono wybór łączy zadań w oknie dialogowym **Edytuj zadanie**.

![Wybieranie łączy zadań w oknie dialogowym Edytuj zadanie.](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Skonfiguruj operację punktu sprzedaży, aby mogła być połączona z zadaniem

Aby skonfigurować operację punktu sprzedaży, aby można ją było połączyć z zadaniem, wykonaj następujące kroki.

1. Przejdź do **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.
1. Wybierz **Edytuj**, znajdź operację punktu sprzedaży, a następnie zaznacz pole wyboru **Włącz zarządzanie zadaniami**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania zadaniami](task-mgmt-overview.md)

[Konfigurowanie zarządzania zadaniami](task-mgmt-configure.md)

[Przypisywanie list zadań do sklepów lub pracowników etatowych](task-mgmt-assign-lists.md)

[Zarządzanie zadaniami w punkcie sprzedaży](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
