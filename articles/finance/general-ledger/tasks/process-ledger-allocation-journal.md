---
title: Przetwarzanie arkusza alokacji księgi
description: W tym temacie wyjaśniono, jak przetwarzać żądania alokacji Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33e989d3641ae1eaa28a55398fcf51674ac1ed72
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446824"
---
# <a name="process-ledger-allocation-journal"></a>Przetwarzanie arkusza alokacji księgi

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak przetwarzać żądania alokacji. Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej. Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Przetwarzanie żądania alokacji**.
2. W polu **Reguła** wybierz odpowiedni rekord z menu rozwijanego.
3. W polu **Na dzień** wprowadź datę.

    - Wartość **Na dzień** jest bardzo ważna, jeżeli źródłem danych reguły jest księga. Ta data określa, które salda księgi mają być uwzględnione w alokacji.  
    - W polu **Źródło zerowe** wybierz opcję **Zatrzymaj**. Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej zero.  

4. W polu **Opcje propozycji** wybierz opcję **Tylko propozycja**. Wybierz opcję **Tylko propozycja**, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.  
5. W polu Data księgowania w księdze głównej wprowadź datę.
6. Kliknij przycisk **OK**.
7. W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Arkusze alokacji**.
8. Wybierz **Linie**.
9. Wybierz opcję **Zaksięguj**.
10. Wybierz opcję **Zaksięguj**.

