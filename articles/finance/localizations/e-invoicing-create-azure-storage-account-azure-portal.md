---
title: Tworzenie konta magazynu usługi Azure w portalu Azure Portal
description: W tym artykule wyjaśniono, jak utworzyć konto magazynu platformy Azure na potrzeby fakturowania elektronicznego.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5eca23985c48f4e577bd4567cc2e324df5aa9690
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291645"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Tworzenie konta magazynu usługi Azure w portalu Azure Portal

[!include [banner](../includes/banner.md)]

Wszystkie pliki elektroniczne, które są generowane przez usługę fakturowania elektronicznego lub przechodzą do usługi podczas przetwarzania, są przechowywane w kontenerach konta magazynu Microsoft Azure. Aby mieć pewność, że fakturowanie elektroniczne będzie mieć dostęp do tych kontenerów, musisz podać token sygnatury dostępu współdzielonego (SAS) konta magazynu dla usługi fakturowania elektronicznego. Ponadto, aby zapewnić, że token jest przechowywany w bezpieczny sposób, nie należy dostarczać bezpośrednio tokenu SAS. Należy go zapisać w kluczu Azure i podać klucz tajny Azure Key Vault.

1. Umożliwia otwarcie konta magazynu, które ma być używane z usługą Faktury elektroniczne.
2. Przejdź do **Ustawienia** \> **Konfiguracja** i upewnij się, że parametr **Zezwalaj na publiczny dostęp do obiektów Blob** jest ustawiony na **Włączone**.
3. Przejdź do **Magazyn danych** \> **Kontenery** i utwórz nowy kontener.
4. Wprowadź nazwę kontenera i ustaw dla pola **Poziom dostępu publicznego** wartość **Prywatne (brak dostępu anonimowego)**.
5. Otwórz kontener i przejdź do **Ustawienia** \> **Polityka dostępu**.
6. Wybierz opcję **Dodaj zasady**, aby dodać zapisane zasady dostępu.
7. Ustaw pole **Identyfikator** zgodnie z potrzebą.
8. W polu **uprawnienia** zaznacz opcję wszystkie uprawnienia.

    ![Wszystkie uprawnienia wybrane w polu Uprawnienia w oknie dialogowym Dodawanie zasad.](media/e-invoicing-azure-1.png)

9. Wprowadź daty rozpoczęcia i zakończenia. Data zakończenia powinna być w przyszłości.
10. Wybierz przycisk **OK**, aby zapisać zasady, a następnie zapisz zmiany w kontenerze.
11. Przejdź do **Ustawienia** \> **Udostępnione tokeny dostępu** i ustaw wartości pól.
12. Wprowadź daty rozpoczęcia i zakończenia. Data zakończenia powinna być w przyszłości.
13. W polu **uprawnienia** wybierz następujące uprawnienia:

    - Odczyt
    - Dodawanie
    - Utwórz
    - Zapisz
    - Usuń
    - Lista

14. Wybierz pozycję **Generuj token SAS i adres URL**.
15. Skopiuj i przechowaj wartość w polu **adresu URL SAS obiektu blob**. Ta wartość będzie używana w dalszej części tej procedury i będzie określana jako *Identyfikator URI podpisu dostępu współdzielonego*.
16. Otwórz magazyn kluczy, którego zamierzasz używać z Faktury elektroniczne.
17. Przejdź do **Ustawienia** \> **Wpis tajny**, a następnie wybierz opcję **Generuj/Importuj**, aby utworzyć wpis tajny.
18. Na stronie **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
19. Pozwala wprowadzić nazwę wpisu tajnego. Ta nazwa będzie używana podczas instalacji usługi w usłudze Regulatory Configuration Service (RCS) i będzie nazywana *nazwą klucza tajnego magazynu kluczy*. Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Service (RCS) – funkcje globalizacji](e-invoicing-set-up-rcs.md).
20. W polu **Wartość** wprowadź skopiowany wcześniej identyfikator URI sygnatury dostępu współdzielonego.
21. Wybierz opcję **Utwórz**.
