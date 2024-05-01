# cursoEPM-1
compartido
Hello

Actualizaciones realizadas por el equipo de:
Liliana María Pérez Villegas
Jhon Jairo Zapata González.

- Adición del cálculo de una nueva característica.
# Calcular una nueva característica
datos_Maestro['ProdENSAPanama'] = datos_Maestro['ENSA'] * datos_Maestro['Panama']

- Adición del gráfico de la matriz de correlación.
# Graficar la matriz de correlación utilizando Seaborn
plt.figure(figsize=(12, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', vmin=-1, vmax=1)
plt.title('Matriz de Correlación')
plt.show()


-- Adición de una nueva gráfica para mostrar los valores reales y a continuación los valores pronosticados.
# Graficar los resultados mejorados
plt.figure(figsize=(12, 6))
plt.plot(datos_Maestro.index, datos_Maestro['ENSA'], label='Historical ENSA', color='blue', marker='o')
plt.plot(predicted_data.index, predicted_data['ENSA_pred'], label='Predicted ENSA for 2024', color='red', linestyle='--', marker='s')
plt.plot([datos_Maestro.index[-1], predicted_data.index[0]], [datos_Maestro['ENSA'].iloc[-1], predicted_data['ENSA_pred'].iloc[0]], color='green', linestyle='-', marker='^')  # Línea uniendo el último punto real con el primer punto pronosticado
plt.title('Historical and Predicted ENSA with Connection Line')
plt.xlabel('Date')
plt.ylabel('ENSA')
plt.legend()
plt.grid(True)
plt.xticks(rotation=45)  # Rotar etiquetas del eje x para mejor legibilidad
plt.tight_layout()  # Ajustar el diseño para evitar superposiciones
plt.show()
