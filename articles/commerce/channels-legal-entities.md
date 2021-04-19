---
title: Utwórz firmy
description: W tym temacie opisano sposób tworzenia firm w Microsoft Dynamics 365 Commerce, która musi zostać utworzona i skonfigurowana przed utworzeniem kanałów.
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
ms.openlocfilehash: 225fd6a07fee29414ac30a4602b4dfccdc4d742b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800622"
---
# <a name="create-legal-entities"></a>Utwórz firmy

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia firm w Microsoft Dynamics 365 Commerce, która musi zostać utworzona i skonfigurowana przed utworzeniem kanałów.

Firma to organizacja, która ma zarejestrowaną lub uchwaloną strukturę prawną. Firmy mogą zawierać zgodne z prawem umowy i wymaga się od nich przygotowywania zestawień na temat ich wydajności.

Firma jest typem podmiotu prawnego. Obecnie firmy to jedyny rodzaj podmiotu prawnego, który można tworzyć, a każdy podmiot prawny jest skojarzony z identyfikatorem firmy. To skojarzenie istnieje, ponieważ niektóre obszary funkcjonalne w programie wykorzystują identyfikator lub *DataAreaId* firmy w ich modelach danych. W tych obszarach funkcjonalnych firmy są używane jako granica zabezpieczeń danych. Użytkownicy mogą uzyskiwać dostęp do danych tylko dla firmy, do której są aktualnie zalogowani. 

Podczas tworzenia kanału należy określić, do której firmy należy dany kanał.

## <a name="create-a-new-legal-entity"></a>Utwórz nową firmę

Aby utworzyć nową firmę w usłudze Dynamics 365 Commerce, należy wykonać następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Ustawienia Headquarters \> Firmy**.
1. W okienku akcji wybierz opcję **Nowy**. Po prawej stronie pojawi się okienko **Nowa firma**.
1. Wprowadź wartość w polu **Nazwa**.
1. Wprowadź wartość w polu **Firma**.
1. W polu **Kraj/region** wprowadź lub wybierz wartość.
1. Kliknij przycisk **OK**. 

   ![Tworzenie firmy](media/legal-entities.png)

1. W sekcji **Ogólne** udostępniane są następujące ogólne informacje o firmie: 
   1. Wprowadź alias, jeśli alias jest wymagany. Alias jest alternatywną nazwą, która może być używana do wyszukiwania danej firmy. 
   1. Zaznacz, czy ta firma jest używana jako skonsolidowana.
   1. Zaznacz, czy ta firma jest używana jako firma z wpisami eliminacji. 
   1. Wybierz **język domyślny** dla firmy. 
   1. Wybierz **strefę czasową** dla firmy.
1. W sekcji **Adresy** wybierz **Edytuj**, żeby wprowadzić takie informacje adresowe, jak nazwa ulicy i numer budynku, kod pocztowy oraz miasto.
1. W sekcji **Informacje kontaktowe** wprowadź informacje dotyczące metod komunikacji, takie jak adresy e-mail, adresy URL i numery telefonów.
1. W sekcji **Raportowanie ustawowe** wprowadź numery rejestrowe używane do raportowania statutowego.
1. W sekcji **Numery rejestracji** wprowadź wszelkie informacje wymagane przez firmę.
1. W sekcji **Informacje o koncie bankowym** wprowadź numery kont bankowych i kody banku rachunków używanych przez firmę.
1. W sekcji **Handel zagraniczny i logistyka** wprowadź informacje wysyłkowe firmy.
1. W sekcji **Sekwencje identyfikatorów** można wyświetlić sekwencje numeracji skojarzone z firmą. Ta opcja będzie pusta na początku.
1. W sekcji **Obraz na pulpit nawigacyjny** można wyświetlić i zmienić obraz logo i pulpitu nawigacyjnego skojarzony z firmą.
1. W sekcji **Rejestracja podatkowa** wprowadź numery rejestrowe używane w zeznaniach dla urzędów skarbowych.
1. W sekcji **Podatek 1099** wprowadź dane formularza 1099 dla firmy.
1. W sekcji **Informacja podatkowa** wprowadź dane podatkowe dla firmy.
1. Wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład szczegółów firmy.

![Sekcja ogólna firmy](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planowanie hierarchii organizacyjnej](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hierarchie organizacyjne](channels-org-hierarchies.md)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
