---
title: Oczyszczanie migracji ER
description: W tym temacie wyjaśniono, jak można za pomocą funkcji oczyszczania migracji ER rozwiązywać problemy z szablonami ER.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: d437bed9b9873f82bcd047e85245bd2a8c66fb3572c06660f29fc19f66aebae1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723148"
---
# <a name="er-migration-cleanup"></a>Oczyszczanie migracji ER 

[!include[banner](../includes/banner.md)]

Podczas zarządzania wystąpieniami aplikacji Finance można zdecydować, czy bieżące wystąpienie ma być migrowane do innej lokalizacji. Na przykład wystąpienie produkcji można migrować do nowego środowiska piaskownicy. Jeśli struktura modułu Raportowanie elektroniczne (ER) została skonfigurowana do przechowywania szablonów w usłudze Microsoft Azure Blob Storage tabela **DocuValue** w nowym środowisku piaskownicy odwołuje się do wystąpienia magazynu obiektów blob w środowisku produkcyjnym. Nie można jednak uzyskać dostępu do tego wystąpienia ze środowiska piaskownicy, ponieważ proces migracji nie obsługuje migracji artefaktów w magazynie obiektów Blob. Należy raczej oczekiwać, że w nowym środowisku piaskownicy będziesz odwoływać się do wystąpienia magazynu obiektów blob w środowisku piaskownicy, które nie uzyskało jeszcze szablonów ER.

W przypadku próby uruchomienia formatu ER, który używa szablonu do generowania dokumentów biznesowych, wystąpi wyjątek i użytkownik zostanie powiadomiony o brakującym szablonie. Użytkownik ma również możliwość użycia opcji oczyszczania migracji ER w celu usunięcia, a następnie ponownego zaimportowania konfiguracji formatu ER, która zawiera szablon.

[![Uruchamianie formatu ER.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Podobny błąd wystąpi, jeśli przejdziesz do strony **Konfiguracje** (**Administracja organizacją** \> **Raportowanie elektroniczne** \> **Konfiguracje**) i w drzewie konfiguracji spróbujesz usunąć konfigurację formatu ER, w której jest używany szablon.

[![Usuwanie formatu ER.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Wykonaj poniższe kroki, aby rozwiązać problemy z szablonami ER, do których nie masz dostępu.

1.  Przejdź na stronę **Administracja organizacją** \> **Okresowe** \> **Oczyszczanie migracji**.
2.  Wybierz konfigurację formatu ER, której nie można wykonać ani usunąć.
3.  Wybierz opcję **Usuń**.
4.  Potwierdź usunięcie wybranej konfiguracji formatu ER.
5.  [Zaimportuj](download-electronic-reporting-configuration-lcs.md) usuniętą konfigurację formatu ER do bieżącego wystąpienia aplikacji Finance.

## <a name="applicability"></a>Możliwość stosowania

> [Ważne] Opcja **Oczyszczanie migracji** jest stosowana tylko w przypadku konfiguracji formatu ER, które zawierają niedostępne szablony ER. Usunięcie konfiguracji formatu ER przy użyciu opcji **Oczyszczanie migracji** spowoduje, że moduł ER usunie szablony związane z artefaktami konfiguracji w jedynej bazie danych aplikacji. Istnienie odpowiednich plików fizycznych w magazynie obiektów blob nie jest weryfikowane. Zamiast tego przyjmuje się, że nie ma takich plików. Dlatego nie należy używać opcji **Oczyszczanie migracji** jako alternatywy opcji usuwania konfiguracji ER na stronie **Konfiguracje**. Używaj opcji **Oczyszczanie migracji** tylko wtedy, gdy działanie opcji usuwania konfiguracji ER na stronie **Konfiguracje** zakończyło się niepowodzeniem.
>
> Jeśli użyjesz opcji **Oczyszczanie migracji** w celu usunięcia konfiguracji formatu ER, gdy przywoływany szablony będzie dostępny w magazynie obiektów blob, usuniesz tylko powiązane artefakty konfiguracji w bazie danych aplikacji. Plik fizyczny szablonu pozostanie w magazynie obiektów blob. Zastąpienie pliku w magazynie obiektów blob nie jest już dozwolone. Aby uzyskać więcej informacji, zobacz [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Ponadto nie będzie już można ponownie importować konfiguracji usuniętych przy użyciu oczyszczania migracji w tym środowisku. Aby rozwiązać ten problem, należy znaleźć odpowiedni plik w magazynie obiektów blob i usunąć go ręcznie.

[![Importowanie formatu ER.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Podobny problem może wystąpić w przypadku migrowania wystąpienia aplikacji do innej lokalizacji, która została użyta jako lokalizacja docelowa migracji, dla której magazyn obiektów blob już zawiera pliki szablonów ER.

Ponieważ możesz mieć kilka konfiguracji formatu ER, ten proces może być czasochłonny. Z tego względu preferowane jest użycie funkcji [tworzenia kopii zapasowych szablonów ER](er-backup-storage-templates.md) do automatycznego odzyskiwania szablonów z przerwanymi odwołaniami.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]