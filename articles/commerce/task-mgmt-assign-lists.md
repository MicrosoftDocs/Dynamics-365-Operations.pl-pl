---
title: Przypisywanie list zadań do sklepów lub pracowników etatowych
description: W tym artykule opisano sposób przypisywania list zadań do sklepów lub pracowników w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: faff772051738f624b86fd23fb6bf29173e909ea
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746202"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Przypisywanie list zadań do sklepów lub pracowników etatowych

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób przypisywania list zadań do sklepów lub pracowników w Microsoft Dynamics 365 Commerce.

Zarządzanie zadaniami w Dynamics 365 Commerce umożliwia przypisywanie listy zadań do wielu sklepów lub pracowników, a także na połączenie sklepów i pracowników. Na przykład Menedżer regionalny dla 20 sklepów może chcieć przypisać listę zadań **Przygotowania do sezonu świątecznego** do wszystkich 20 sklepów.

## <a name="start-the-task-list-assignment-process"></a>Uruchamianie procesu przypisania listy zadań

Zanim rozpoczniesz proces przydzielania zadań, upewnij się, że utworzyłeś listę zadań, wykonując czynności opisane w artykule [Tworzenie list zadań i dodawanie zadań](task-mgmt-create-lists.md). Aby rozpocząć proces przypisywania listy zadań, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.
1. Umożliwia wybór listy zadań do przypisania.
1. Wybierz **Rozpocznij proces**.
1. W oknie dialogowym **Rozpocznij proces**, na karcie **ogólne**, w polu **Nazwa procesu** wprowadź nazwę (na przykład **Sklepy regionu wschodniego**).
1. W polu **Data docelowa** wybierz datę.
1. Aby przypisać listę zadań do sklepów, na karcie **Sklepy** skorzystaj z filtru **Hierarchia organizacji**, aby znaleźć i wybrać sklepy.

    Aby przypisać listę zadań do pracowników, na karcie **Pracownicy** znajdź i zaznacz pracowników.

1. Wybierz przycisk **OK**, aby rozpocząć proces. Lista zadań jest przypisana do wybranych sklepów lub pracowników.

Na poniższej ilustracji przedstawiono przykład wyszukiwania i wybierania sklepów w oknie dialogowym **Rozpocznij proces**.

![Znajdowanie i wybieranie sklepów w oknie dialogowym Rozpocznij proces.](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Umożliwia przypisywanie list zadań na podstawie cyklu

Czasami detalista ma powtarzalne zadania, takie jak „Lista kontrolna czwartek” lub „Lista kontrolna pierwszego dnia miesiąca”. W związku z tym może zaistnieć konieczność cyklicznego przypisywania listy zadań.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.
1. Umożliwia wybór listy zadań do przypisania.
1. Wybierz **Rozpocznij proces**.
1. W oknie dialogowym **Rozpocznij proces**, na karcie **ogólne**, w polu **Nazwa procesu** wprowadź nazwę.
1. Ustaw opcję **Cykl** na **Tak**.
1. W polu **Przesunięcie daty docelowej cyklu w dniach** wprowadź liczbę dni. Jeśli na przykład zostanie wprowadzona wartość **4**, datą docelową jest data cyklu plus cztery dni.
1. Na karcie **Uruchom w tle** wybierz **Cykl**.
1. W oknie dialogowym **Zdefiniuj cykl** wprowadź kryteria częstotliwości, a następnie wybierz przycisk **OK**.

Na poniższej ilustracji przedstawiono przykład sposobu wprowadzania kryteriów częstotliwości w oknie dialogowym **Definiowanie cyklu**.

![Wprowadzanie kryteriów częstotliwości w oknie dialogowym Zdefiniuj cykl.](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Śledzenie stanu listy zadań

Jeśli jesteś menedżerem regionalnym lub menedżerem sklepu, możesz śledzić stan list zadań przypisanych do wielu sklepów lub pracowników. Następnie można kontynuować działanie z sklepami lub pracownikami, które nie wypełnili przydzielonych im zadań w czasie. Biuro zaplecza w Commerce umożliwia przeglądanie stanu list zadań, ponowne przypisywanie zadań lub zmianę stanu zadania.

Aby śledzić stan listy zadań dla wszystkich zadań, należy wykonać następujące kroki.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Procesy zarządzania zadaniami**.
1. Wybierz kartę **Wszystkie listy zadań,** aby wyświetlić stan wszystkich list zadań przypisanych do różnych sklepów.

Aby śledzić stan listy zadań dla wszystkich zadań przypisanych do Ciebie, należy wykonać następujące kroki.

1. Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Procesy zarządzania zadaniami**.
1. Wybierz kartę **Moje zadania** lub **Wszystkie zadania**, aby wyświetlić lub zaktualizować stan przydzielonych zadań.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania zadaniami](task-mgmt-overview.md)

[Konfigurowanie zarządzania zadaniami](task-mgmt-configure.md)

[Tworzenie list zadań i dodawanie zadań](task-mgmt-create-lists.md)

[Zarządzanie zadaniami w punkcie sprzedaży](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
