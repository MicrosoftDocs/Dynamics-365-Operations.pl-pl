---
title: Ogranicz edytowanie informacji osobistych
description: Ograniczanie pracownikom możliwości edytowania szczegółów kontaktu w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 98cb7c2f1f57dacf303e2e9bc7779ce3ede6733e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695880"
---
# <a name="restrict-editing-of-personal-information"></a>Ogranicz edytowanie informacji osobistych


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

W tym temacie opisano sposób ograniczenia możliwości edytowania szczegółów kontaktów przez pracowników w Dynamics 365 Human Resources. Możesz chcieć uniemożliwić pracownikom edytowanie niektórych danych kontaktowych, takich jak lokalizacja firmy lub adres e-mail.

> [!NOTE]
> Aby można było korzystać z tej funkcji, należy najpierw włączyć funkcję **(Wersja zapoznawcza) Ogranicz pracownikom możliwość dodawania lub edytowania adresów i informacji kontaktowych w wybranych celach** w Zarządzaniu funkcjami. Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).<br><br>![Włącz funkcje w wersji Preview.](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Wybierz informacje, które pracownik może dodać lub edytować

1. W Human Resources wybierz opcję **Zarządzanie kadrami**, wybierz opcję **Łącza**, a następnie wybierz **Parametry Human Resources**.

   ![Przejdź do parametrów zasobów ludzkich.](./media/hr-employee-self-service-human-resources-parameters.png)

2. Na stronie **Parametry zasobów ludzkich** wybierz kartę **Samoobsługa pracownika etatowego**.

   ![Wybierz opcję Samoobsługa pracownika etatowego.](./media/hr-employee-self-service-tab.png)

3. Na karcie **Samoobsługa pracownika etatowego** usuń zaznaczenie wszystkich informacji w sekcji **Adres i informacje kontaktowe**, których nie chcesz, aby pracownicy mogli dodawać ani edytować. W tym przykładzie odznaczyliśmy informacje o kontakcie **Biznesowym**.

   ![Ogranicz edytowanie informacji o kontakcie biznesowym.](./media/hr-employee-self-service-restrict-business.png)

4. Wybierz opcję **Zapisz**.

   ![Zapisz zmiany.](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Doświadczenie pracownika

Gdy ograniczysz pracownikom możliwość dodawania lub edytowania danych kontaktowych, będą mogli wyświetlać te informacje, ale nie mogą ich zmienić.

W tym przykładzie pracownicy, kiedy pracownicy nie mogą edytować szczegółów kontaktów **biznesowych**, nadal mogą zobaczyć te informacje w formularzu **Samoobsługa pracownika etatowego**:

![Wyświetl szczegóły kontaktu biznesowego.](./media/hr-employee-self-service-restrict-view.png)

Jednak po wybraniu szczegółów kontaktu biznesowego okienko **Edycja adresu** jest wyświetlane jako tylko do odczytu i nie można zmienić żadnego z pól.

![Szczegóły kontaktu biznesowego są wyświetlane jako tylko do odczytu.](./media/hr-employee-self-service-restrict-read-only.png)

Ponadto, jeśli wybiorą opcję **Dodaj**, aby dodać nowy adres, nie będą mogli wybrać opcji **Firma** z listy rozwijanej **Cel**.

![Pracownik nie może dodać adresu firmy.](./media/hr-employee-self-service-restrict-add.png)

Pracownicy mają takie same wrażenia, gdy wybierają **Dane kontaktowe** na stronie **Informacje osobiste** i dodają nowy adres. Na liście rozwijanej **Cel** są wyświetlane tylko typy informacji, które mogą dodawać. 

![Pracownik nie może wybrać firmy z listy rozwijanej Cel.](./media/hr-employee-self-service-restrict-purpose.png)

**Szczegóły osoby kontaktowej** będą teraz wyświetlać **Cel** w siatce.

![Cel jest wyświetlany w siatce szczegółów kontaktu.](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md)<br>
[Konfigurowanie parametrów rozwiązania Human Resources](hr-setup-parameters.md)<br>
[Edytowanie informacji osobistych](hr-employee-manager-self-service-edit-personal-information.md)
