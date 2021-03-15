---
title: Tworzenie list zadań i dodawanie zadań
description: W tym temacie opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006217"
---
# <a name="create-task-lists-and-add-tasks"></a>Tworzenie list zadań i dodawanie zadań

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

*Zadanie* definiuje określony element pracy lub akcję, którą ktoś musi zakończyć w dniu lub przed określonym terminem płatności. W Dynamics 365 Commerce zadanie może zawierać szczegółowe instrukcje i informacje o osobie kontaktowej. Może również zawierać łącza do operacji związanych z kopiami zapasowymi, operacje punktu sprzedaży (POS) lub stron witryny w celu zwiększenia produktywności i zapewnienia kontekstu potrzebnego właścicielowi zadania w celu efektywnego wykonania zadania.

*Lista zadań* to zbiór zadań, które należy wykonać w ramach procesu biznesowego. Na przykład może to być lista zadań, którą nowy pracownik musi zakończyć w celu przechodzenia do systemu, listy zadań dla kasjerów, którzy pracują wieczorem lub z listy zadań, które muszą zostać wypełnione, aby przygotować sklep do nadchodzącego sezonu wakacyjnego. W Commerce, każda lista zadań z datą docelową może zostać przypisana do dowolnej liczby sklepów lub pracowników i może zostać skonfigurowana do ponownego wystąpienia.

Zarówno kierownicy, jak i pracownicy mogą tworzyć listy zadań w biurze zaplecza w Commerce, a następnie przypisywać je do zbioru sklepów.

## <a name="create-a-task-list"></a>Utwórz nową listę zadań

Aby utworzyć listę zadań, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.
1. Wybierz **Nowy**, a następnie wprowadź wartości w polach **Nazwa**, **Opis** i **Właściciel**.
1. Wybierz opcję **Zapisz**.

## <a name="add-tasks-to-a-task-list"></a>Dodawanie zadań do listy zadań

Aby dodać zadanie do listy zadań, wykonaj następujące kroki.
 
1. Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Nowe**, aby dodać zadanie.
1. W nowym oknie dialogowym **Utwórz nowe zadanie**, w polu **Nazwa** wprowadź unikatową nazwę zadania.
1. W polu **Przesunięcie danych należnych od daty docelowej** wprowadź dodatnią lub ujemną wartość całkowitą. Na przykład wprowadź **-2**, jeśli zadanie ma zostać wykonane dwa dni przed datą ukończenia listy zadań.
1. W polu **Uwagi** wprowadź szczegółowe instrukcje.
1. W polu **Osoba kontaktowa** wprowadź nazwisko eksperta, którego właściciel zadania może skontaktować się, jeśli wymaga tego pomoc.
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

![Wybieranie łączy zadań w oknie dialogowym Edytuj zadanie](media/HQ-POS-Tasks-Linking.png)

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