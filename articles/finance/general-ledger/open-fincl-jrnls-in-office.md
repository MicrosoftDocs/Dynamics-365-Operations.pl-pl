---
title: Otwieranie szablonów arkuszy finansowych w pakiecie Office
description: W tym artykule opisano problemy, które mogą wystąpić podczas tworzenia niestandardowych arkuszy finansowych przy użyciu szablonu programu Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896355"
---
# <a name="open-financial-journal-templates-in-office"></a>Otwieranie szablonów arkuszy finansowych w pakiecie Office

[!include [banner](../includes/banner.md)]

W tym artykule opisano problemy, które mogą wystąpić podczas tworzenia niestandardowych arkuszy finansowych przy użyciu szablonu programu Microsoft Excel.

## <a name="symptom"></a>Objaw

Utworzono niestandardowy szablon programu Excel dla arkuszy finansowych, ale nie jest on wyświetlany w menu **Otwórz wiersze w programie Excel**. Może on także być widoczny w menu, jednak po jego wybraniu otwiera się inny szablon.

## <a name="resolution"></a>Rozwiązanie

Domyślna funkcja otwierania w programie Excel używa głównego źródła danych (tabeli) bieżącej strony w celu określenia, które szablony lub jednostki danych pakietu Office mają być wyświetlane jako opcje w menu **Otwórz w programie Excel**. Takie zachowanie programu nie sprawdza się idealnie w przypadku arkuszy finansowych, ponieważ arkusze finansowe używają tych samych tabel (LedgerJournalTable i LedgerJournalTrans), które są głównym źródłem danych wielu innych typów arkuszy.

W przypadku arkuszy finansowych funkcja Otwórz wiersze w programie Excel ma na celu wyświetlanie szablonów, które zostały zaprojektowane z myślą o rodzaju arkusza, z którym aktualnie pracujesz, takim jak arkusz finansowy lub arkusz płatności. Na przykład szablon, który jest przeznaczony do użytku z arkuszem płatności dostawcy, będzie zaprojektowany tak, by wymusić wybór Twojego głównego konta jako konta dostawcy.

Jeśli chcesz podwyższyć poziom szablonu tak, aby był on dostępny w menu **Otwórz wiersze w programie Excel** i **Otwórz w programie Excel**, najłatwiej będzie zaimplementować interfejs **LedgerIJournalExcelTemplate** i rozszerzyć klasę **DocuTemplateRegistrationBase**. W systemie można się spotkać z wieloma zaimplementowanymi przykładami takiego podejścia. Jednym z przykładów, którego można użyć na potrzeby odwołania, jest interfejs **LedgerDailyJournalExcelTemplate** utworzony dla arkusza finansowego (lub arkusza dziennego).

Gdy dla szablonu zostanie zaimplementowany interfejs **LedgerIJournalExcelTemplate**, w menu **Otwórz wiersze w programie Excel** szablony będą filtrowane według typu arkusza i będą wyświetlane tylko szablony dostępne dla danego arkusza. Interfejs zapewnia również metodę weryfikacji, która gwarantuje, że nie można otworzyć dla arkusza szablonu, jeśli nie spełnia on wymagań dotyczących typu konta. Można na przykład określić typ konta **Dostawca** lub **Księga**.

Aby uzyskać więcej informacji o tej funkcji, patrz temat [Dodawanie szablonów do menu Otwórz wiersze w programie Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
