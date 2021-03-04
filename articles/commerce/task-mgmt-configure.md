---
title: Konfigurowanie zarządzania zadaniami
description: W tym temacie opisano sposób konfigurowania funkcji zarządzania zadaniami w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 9a4775c2dba2b9aa8e671ab6c246000303b3a37e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415006"
---
# <a name="configure-task-management"></a>Konfigurowanie zarządzania zadaniami

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania funkcji zarządzania zadaniami w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Aby menedżerowie i pracownicy Dynamics 365 Commerce mogli skorzystać z funkcji zarządzania zadaniami w Commerce, należy skonfigurować funkcję zarządzania zadaniami. Kroki konfiguracyjne obejmują przyznawanie uprawnień menedżerom i pracownikom, dystrybuowanie uprawnień do klientów punktu sprzedaży (POS), konfigurowanie powiadomień punktu sprzedaży oraz konfigurowanie kafelka **Zadania** na stronie głównej aplikacji punktu sprzedaży.

## <a name="configure-permissions-for-store-managers"></a>Konfigurowanie uprawnień dla menedżerów sklepów

Każdy pracownik w danym sklepie może wyświetlać wszystkie zadania przypisane do danego sklepu. Mogą również aktualizować stan przypisanych do nich zadań. Jednak osoby, takie jak kierownicy sklepów, muszą mieć uprawnienia do zarządzania zadaniami, aby zarządzać zadaniami przypisanymi do sklepu i tworzyć zadania jednorazowe.

Aby skonfigurować uprawnienia zarządzania zadaniami dla menedżerów sklepów, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Pracownicy \> Grupy uprawnień**.
1. Wybierz określoną grupę uprawnień (na przykład **Menedżer**), a następnie wybierz opcję **Edytuj**.
1. Na skróconej karcie **Uprawnienia**, w opcji **Zezwalaj na zarządzanie zadaniami** określ wartość **Tak**.
1. Na skróconej karcie **Powiadomień** dodaj operację **Zarządzania zadaniami** i wprowadź wartość w polu **Kolejność wyświetlania**. Na przykład wprowadzenie wartości **2**, jeśli dla operacji **Realizacji zamówienia** istnieje już wartość **Kolejność wyświetlania** **1**.
    
> [!NOTE]
> Jeśli osoba niebędąca na stanowisku menedżera musi mieć uprawnienia do zarządzania zadaniami w punkcie sprzedaży, można udzielić uprawnienia do danej osoby. Można również utworzyć nową grupę uprawnień dla innych niż menedżerów i ustawić opcję **Zezwalaj na zarządzanie zadaniami** na **Tak**.

Poniższa ilustracja pokazuje, jak skonfigurować uprawnienia do zarządzania zadaniami dla menedżerów sklepów.

![Konfigurowanie uprawnienia zarządzania zadaniami dla menedżerów sklepów](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Konfigurowanie uprawnień pracowników

Pracownicy muszą mieć uprawnienia do tworzenia list zadań, zarządzania kryteriami przypisywania i konfigurowania powtarzania dowolnej listy zadań. Aby skonfigurować te uprawnienia, należy przypisać pracowników do roli **Menedżer zadań sieci sprzedaży**.

Aby skonfigurować uprawnienia dla pracownika, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Retail and Commerce \> Pracownicy \> Użytkownicy**.
1. Wybierz pracownika.
1. Na karcie skróconej **Role użytkownika** wybierz opcję **Przypisz role**.
1. W oknie dialogowym **Przypisz role do użytkownika** wybierz rolę **Menedżer zadań sieci sprzedaży**, a następnie kliknij przycisk **OK**.

## <a name="distribute-permissions-to-pos-clients"></a>Dystrybuuj uprawnienia do klientów punktu sprzedaży

Zanim pracownicy będą mogli skorzystać z klientów punktu sprzedaży, muszą być oni dystrybuowane i zsynchronizowane z tymi klientami.

Aby dystrybuować uprawnienia do klientów punktu sprzedaży, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Wybierz harmonogram dystrybucji **1060** (**Personel**), a następnie wybierz opcję **Uruchom teraz**.
1. Wybierz harmonogram dystrybucji **1070** (**Konfiguracja kanału**), a następnie wybierz opcję **Uruchom teraz**.

## <a name="configure-pos-notifications-for-tasks"></a>Konfigurowanie powiadomień punktu sprzedaży dla zadań

Należy skonfigurować zarządzanie zadaniami, aby były dostępne powiadomienia w aplikacji punktu sprzedaży.

Aby skonfigurować powiadomienia punktu sprzedazy dla zadań, wykonaj poniższe kroki.

1. Przejdź do **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.
1. Znajdź operację **1400** (**Zarządzanie zadaniami**) i zaznacz pole wyboru **Włącz powiadomienia**.

Na poniższej ilustracji przedstawiono operację **Zarządzania zadaniami** na stronie **Operacje punktu sprzedaży**.

![Operacja zarządzania zadaniami na stronie operacji punktu sprzedaży](media/HQ-POS-Tasks-Notifications.png)

Aby uzyskać więcej informacji o konfigurowaniu powiadomień punktu sprzedaży, zapoznaj się z tematem [Pokazywanie powiadomień o zamówieniach w aplikacji punktu sprzedaży (POS)](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Konfiguruj kafelek zadania na stronie głównej aplikacji punktu sprzedaży

Przed skonfigurowaniem kafelka **Zadania** na stronie głównej aplikacji punktu sprzedaży należy zapoznać się z [Układy ekranu w aplikacji punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania i dodawania nowych przycisków do układu ekranu punktu sprzedaży.

Aby skonfigurować kafelek **Zadania** na stronie głównej aplikacji punktu sprzedaży, postępuj zgodnie z następującymi krokami.

1. Wybierz kolejno opcje **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.
1. Wybierz układ ekranu, wybierz rozmiar układu i wybierz siatkę przycisków.
1. Na skróconej karcie **Siatki przycisków** wybierz opcję **Projektant**, aby edytować wybraną siatkę przycisków.
1. Dodaj kafelek **Zadania** do odpowiedniej sekcji strony głównej.

Poniższa ilustracja przedstawia przykład kafelka **Zadania** na stronie głównej punktu sprzedaży.

![Kafelek zadań na stronie głównej punktu sprzedaży](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania zadaniami](task-mgmt-overview.md)

[Tworzenie list zadań i dodawanie zadań](task-mgmt-create-lists.md)

[Przypisywanie list zadań do sklepów lub pracowników etatowych](task-mgmt-assign-lists.md)

[Zarządzanie zadaniami w punkcie sprzedaży](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]