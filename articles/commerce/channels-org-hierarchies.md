---
title: Konfigurowanie hierarchii organizacyjnych
description: W tym temacie opisano sposób konfigurowania hierarchii organizacyjnych w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f6e791ffd15128d2076340515a08b5ea6be70dae
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346015"
---
# <a name="set-up-organization-hierarchies"></a>Konfigurowanie hierarchii organizacyjnych

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania hierarchii organizacyjnych w Microsoft Dynamics 365 Commerce.

Przed utworzeniem kanałów należy upewnić się, że zostały skonfigurowane hierarchie organizacyjne.

Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw. Można na przykład skonfigurować jedną hierarchię na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych. Następnie można ustawić inną hierarchię do raportowania informacji finansowych nie wymaganych przez prawo, ale używanych w raportach wewnętrznych.

Przed utworzeniem hierarchii organizacyjnej należy utworzyć organizacje. Aby uzyskać więcej informacji, zobacz zadania [Tworzenie firmy](channels-legal-entities.md) lub [Tworzenie jednostki operacyjnej](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Aby uzyskać więcej informacji, zobacz następujące tematy.
- [Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Planowanie hierarchii organizacyjnej](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Tworzenie hierarchii organizacyjnej](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Tworzenie hierarchii organizacyjnej

Aby utworzyć hierarchię organizacyjną, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Hierarchie organizacyjne**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź wartość w polu **Nazwa**.
1. W sekcji **Cel** wybierz **Przypisywanie celu**.
1. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz cel, który zostanie przypisany do hierarchii organizacyjnej.
1. W sekcji **Przypisane hierarchie** wybierz **Dodaj**.
1. Na liście oznacz wybrany wiersz. Znajdź właśnie utworzoną hierarchię.
1. Kliknij przycisk **OK**.

Poniższy rysunek przedstawia przykładową hierarchię organizacyjną utworzoną dla fikcyjnego zbioru sklepów „Adventure Works”.

![Przykład hierarchii organizacyjnej.](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Dodawanie organizacji do hierarchii

Aby dodać organizację do hierarchii, wykonaj następujące kroki.

1. Na liście znajdź i zaznacz odpowiedni rekord. Zaznacz hierarchię.
1. Na okienku akcji wybierz opcję **Widok**.
1. W razie potrzeby dodaj organizację.
1. Aby dodać organizację, wybierz opcję **Edytuj**, a następnie wybierz opcję **Wstaw**. Po zakończeniu wprowadzania zmian można zapisać wersję roboczą i opublikować zmiany.

Na poniższej karcie przedstawiono firmę dodaną w katalogu głównym hierarchii z czterema centrami kosztów dodanymi do kanałów „biurowych”, „gniazd”, „online” i „biura obsługi”. Do każdego z nich można dodać różne gniazda sieci sprzedaży, biura obsługi i kanały online.

![Przykład projektanta hierarchii.](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planowanie hierarchii organizacyjnej](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Tworzenie firm](channels-legal-entities.md)

[Tworzenie jednostek operacyjnych](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
