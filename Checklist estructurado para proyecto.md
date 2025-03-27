# ✅ Checklist estructurado para proyectos de Machine Learning

## 🔍 1. Entendimiento del problema
- [ ] ¿Cuál es el objetivo del modelo?
- [ ] ¿Cuál es la variable objetivo (target)?
- [ ] ¿Qué métrica es más importante? (`accuracy`, `f1`, `recall`, etc.)
    ¿Qué métrica es más importante?
        Dependiendo del objetivo, las métricas pueden cambiar. Algunas opciones son:

        Accuracy: mide cuántas predicciones fueron correctas. Pero no siempre es confiable, especialmente con clases desbalanceadas (por ejemplo, si solo sobrevivieron pocos).

        Precision (precisión): Mide cuántos de los predichos como "sobrevivientes" realmente lo fueron. Es importante si no quieres que el modelo haga muchas predicciones incorrectas sobre personas que no sobrevivieron.

        Recall (sensibilidad): Mide cuántos de los sobrevivientes reales fueron identificados por el modelo. Es clave si te interesa no perder sobrevivientes (por ejemplo, en un contexto real, queremos identificar a todos los posibles sobrevivientes, aunque haya más falsos positivos).

        F1-score: Es un balance entre precision y recall. Es útil si la distribución de clases es desbalanceada y quieres evitar que el modelo se incline demasiado hacia una de las clases.

        ROC-AUC: Mide la habilidad del modelo para diferenciar entre las clases (la curva del "Receiver Operating Characteristic"). Es útil cuando quieres ver cómo el modelo clasifica en términos de tasa de verdaderos positivos y falsos positivos.

- [ ] ¿Qué significan un FP y un FN para el problema?

## 📊 2. Exploración del dataset
- [ ] Cargar el dataset crudo
- [ ] Revisar `.info()`, `.describe()`, `.head()`
- [ ] Identificar valores faltantes
- [ ] Observar la distribución de cada variable
- [ ] Verificar si hay clases desbalanceadas

## 🧹 3. Preprocesamiento inicial
- [ ] Imputar valores faltantes con lógica justificada
- [ ] Eliminar o transformar outliers si es necesario
- [ ] Codificar variables categóricas correctamente
- [ ] Normalizar/escalar si es requerido por el modelo

## 🧠 4. Feature Engineering
- [ ] Crear variables nuevas basadas en hipótesis
- [ ] Generar interacciones útiles entre columnas
- [ ] Reducir cardinalidad en variables categóricas si es necesario
- [ ] Documentar cada nueva feature y por qué se creó

## ✂️ 5. División del dataset
- [ ] Separar en `train` y `test` (o `validation`)
- [ ] Asegurar que la división sea **estratificada** si hay desbalance

## ⚙️ 6. Modelos base
- [ ] Entrenar varios modelos simples sin tuning
- [ ] Comparar con una métrica elegida
- [ ] Seleccionar 1 o 2 para seguir optimizando

## 🔧 7. Optimización de hiperparámetros
- [ ] Usar `GridSearchCV`, `RandomSearchCV`, etc.
- [ ] Evaluar con validación cruzada
- [ ] Registrar la mejor combinación de hiperparámetros

## 📈 8. Evaluación final
- [ ] Medir en test: `accuracy`, `precision`, `recall`, `f1`, `ROC-AUC`
- [ ] Ver matriz de confusión
- [ ] Confirmar que el modelo no está sobreajustado

## 🔍 9. Interpretabilidad
- [ ] Revisar `feature_importances_` o usar SHAP/LIME
- [ ] Validar que el modelo esté tomando decisiones razonables
- [ ] Documentar interpretaciones clave

## 🧪 10. Deploy o entrega
- [ ] Armar `submission.csv` o pipeline final
- [ ] Dejar el código limpio y modular
- [ ] Documentar conclusiones, limitaciones y próximos pasos
