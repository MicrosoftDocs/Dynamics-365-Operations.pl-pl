---
title: Konfigurowanie kategorii konta głównego
description: W tym temacie wyjaśniono sposób konfigurowania kategorii konta głównego w Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 957fdc184410dc85f54cd3163799a9003f0727bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222226"
---
# <a name="set-up-main-account-categories"></a>Konfigurowanie kategorii konta głównego

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania kategorii konta głównego. Kategorie kont głównych są używane dla domyślnych raportów w sprawozdawczości finansowej i programie Power BI. Kategoriom kont głównych, które są tworzone domyślnie, można zmienić nazwy, ale nie można ich usunąć. Można tworzyć dodatkowe kategorie kont i używać ich na potrzeby raportowania i analizy. Ten temat wykorzystuje firmę demonstracyjną „USMF”.

## <a name="create-a-main-account-category"></a>Tworzenie kategorii konta głównego
1. W okienku nawigacji wybierz kolejno **Moduły > Księga główna > Plan kont > Konta > Kategorie kont głównych**.
2. Wybierz pozycję **Nowy**.
3. W polu **Kategoria konta głównego** wprowadź unikatową nazwę.
4. W **polu Opis** wprowadź opis kategorii kont głównych.
5. W polu **Typ konta głównego** zaznacz typ konta głównego, który zostanie powiązany z kategorią.

## <a name="link-main-accounts-to-account-category"></a>Łączenie kont głównych z kategorią konta
1. Kliknij opcję **Połącz konta główne**.
2. Z listy wybierz konta główne, które mają zostać przypisane do kategorii konta głównego, zaznaczając odpowiednie pola w **Połączonej** kolumnie. Przypisanie kont głównych do kategorii konta głównego spowoduje agregację sald kont, gdy ta kategoria jest używana do sprawozdawczości finansowej i analizy.  
3. Zaznacz lub wyczyść pole wyboru **Połączone**, aby wybrać konta główne.
4. Kliknij przycisk **OK**.
5. Wybierz opcję **Tak**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]