---
title: Stany cyklu życia składnika majątku
description: W tym temacie wyjaśniono stany cyklu życia składników majątku i modele cyklu życia w zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 55139c6458e569b15518f0f11f1c12c3a26cae2f26c6a2046a7ebdc1277cb144
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722470"
---
# <a name="asset-lifecycle-states"></a>Stany cyklu życia składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono stany cyklu życia składników majątku i modele cyklu życia w zarządzaniu składnikami majątku. Stany cyklu życia składnika majątku są używane do definiowania, czy składnik majątku jest aktywny czy nieaktywny. Można na przykład skonfigurować stany cyklu życia składnika majątku, takie jak **Utworzone**, **Aktywne** i **Zakończone**.

> [!NOTE]
> - Stany cyklu życia żądania są połączone ze stanami cyklu życia składnika majątku. Dlatego kiedy żądanie zostanie zmienione na nowy stan cyklu życia żądania, składnik majątku, dołączony do żądania jest zmieniany na nowy stan cyklu życia składnika majątku. Na przykład, jeśli stan cyklu życia żądania zostanie zmieniony na **Przychodzący**, stan cyklu życia dołączonego składnika majątku zostanie zmieniony na stan cyklu życia wybranego w polu **stan cyklu życia przychodzącego** na skróconej karcie **Stan cyklu życia składnika majątku** na stronie **Modele stanu cyklu życia składnika majątku**. 


Stany cyklu życia składnika majątku można skonfigurować w modelach cyklu życia składnika majątku, w których można zdefiniować wymagane stany cyklu życia dla różnych typów składnika majątku. Najpierw konfiguruje się stany cyklu życia. Następnie należy utworzyć model cyklu życia i wybrać niego stan cyklu życia.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Stany cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy stan cyklu życia składnika majątku.
3. W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.
4. W polu **Nazwa** wprowadź opis.

    Pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia składnika majątku, które używają stanu cyklu życia składnika majątku.

5. Ustaw opcję **Aktywny** na **Tak**, jeśli stan cyklu życia powinien być aktywnym stanem cyklu życia (innymi słowy, jeśli zlecenia pracy mogą być tworzone dla składników majątku, które są w tym stanie cyklu życia).
6. Ustaw opcję **Usuń otwarte wiersze kalendarza** na **Tak**, jeśli otwarte wiersze kalendarza składnika majątku, które mają stan cyklu życia składnika majątku **Utworzony**, powinny zostać usunięte, gdy są w tym stanie cyklu życia. To ustawienie jest przydatne, jeśli chcesz wyczyścić wszystkie otwarte harmonogramy konserwacji, które nie są już istotne dla składnika majątku (na przykład, jeśli składnik majątku nie jest już aktywny).

> [!NOTE]
> Stany cyklu życia składnika majątku, modele cyklu życia składnika majątku i typy składnika majątku są powiązane. Są one używane w taki sam sposób jak stany cyklu życia zlecenia pracy, modele cyklu życia zlecenia pracy i typy zleceń pracy. 


Po utworzeniu stanów cyklu życia wymaganego składnika majątku można skonfigurować stany cyklu życia w modelach cyklu życia składnika majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Modele cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy model cyklu życia składnika majątku.
3. W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.
4. W polu **Nazwa** wprowadź opis.

    Pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia składnika majątku, które są wybrane w modelu cyklu życia składnika majątku. Pole **Typy składników majątku** zawiera liczbę typów składników majątku, które są używane w modelu cyklu życia.

5. Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia składnika majątku, które powinny być uwzględnione w modelu cyklu życia składnika majątku:

    - Aby uwzględnić stanu cyklu życia w modelu, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo.](media/15-setup-for-objects.png) , aby przenieść ją do wybranej sekcji **Stany cyklu życia**.
    - Aby użyć wszystkich dostępnych stanów cyklu życia dla modelu, wybierz przycisk **Wszystkie dostępne stany cyklu życia** ![Wszystkie dostępne stany cyklu życia.](media/20-setup-for-objects.png). Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.
    - Aby usunąć stanu cyklu życia z modelu, zaznacz go w sekcji **wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki w lewo ![Strzałka w lewo.](media/16-setup-for-objects.png) , aby przenieść ją do wybranej sekcji **Pozostałe stany cyklu życia**.

6. Wybierz pozycję **Aktualizacje stanu cyklu życia**, aby określić stany cyklu życia składnika majątku, które mogą być wybranym stanem cyklu życia.
7. Możesz użyć skróconej karty **Stan składnika majątku**, jeśli obsługujesz składniki majątku otrzymywane do naprawy. W sekcji **Przychodzące/wychodzące** można wybrać stany cyklu życia składnika majątku, aby wskazać przepływ pracy dla składnika majątku otrzymywanego w celu naprawy. Jeśli użyczasz składników majątku klientom lub oddziałom, w sekcji **Użyczenie** wybierz stany cyklu życia użyczonych składników majątku.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]