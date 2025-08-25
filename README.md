Я не мог ждать и решил починить его сам

Сколько кадров в секунду я получу

Я нашёл способ изменить поле зрения и повысить FPS, настроив параметры теней, декалей, заморозив некоторые физические эффекты (например, Ragdolls и разрушение объектов), уменьшив количество фрагментов при разрушении объектов, снизив максимальное расстояние рендеринга для объектов и отключив или уменьшив такие эффекты, как частицы, HDR, SSAO, туман и другие. Если вы хотите снять видео об этой конфигурации, укажите меня в титрах, мне это очень поможет

Все эти команды на самом деле работают, но они скрыты по умолчанию — вы не можете просто запустить их в консоли или в video.txt. Вместо этого вам нужно добавить их в gameinfo.gi

Не ждите значительного повышения FPS, но производительность заметно улучшится, особенно во время командных сражений. Я буду обновлять этот пост по мере обнаружения новых настроек, так что следите за обновлениями!

Чтобы использовать мои настройки, вам нужно открыть файл gameinfo.gi, расположенный в папке с игрой "steam\steamapps\common\Deadlock\game\citadel". Найдя файл, вы увидите строку под названием "ConVars". После первой скобки вставьте мой код.

Пример:

ConVars
{
(здесь вводится команда)

"ставка"
{
"мин." "98304"
"по умолчанию" "786432"
"макс." "1000000"
}

CMD:

// ================ НАСТРОЙКИ ГРАФИКИ ================ 
// Качество ядра
"gpu_level" "0"                     // Минимальный уровень детализации шейдера
"cpu_level" "0"                     // Минимальный уровень детализации эффекта
"mat_set_shader_quality" "0"

// Поле обзора
"r_aspectratio" "1.75"              // 1.75= 80fov | 2.15=90fov | 2.49 = 100fov

// Освещение и тени
"r_directlighting" "0"
"r_ssao" "0"                        // Отключить внешнюю окклюзию
"lb_enable_shadow_casting" "0"
"lb_csm_draw_alpha_tested" "0"
"lb_csm_draw_translucent" "0"
"lb_barnlight_shadowmap_scale" "0.5"
"lb_csm_cascade_size_override" "1"
"lb_dynamic_shadow_resolution_quantization" "128"
"r_citadel_sun_shadow_slope_scale_depth_bias" "1.0" // Туман и атмосфера
"r_enable_volume_fog" "0"
"r_enable_gradient_fog" "0"
"r_enable_cubemap_fog" "0"
"volume_fog_intermediate_textures_hdr" "0"

// Небо и окружающая среда
" r_draw3dskybox" "0"
"r_drawskybox" "1"                  // Установите значение 0, чтобы отключить skybox
"r_monitor_3dskybox" "0"

// SSAO и
"r_citadel_ssao_bent_normals" "накладные"
"r_citadel_ssao_denoise_passes" "0"
"r_citadel_ssao_quality" "0"
"r_citadel_ssao_radius" "0"
"r_citadel_ssao_thin_occluder_compensation" "0" // ================ СИСТЕМА ЧАСТИЦ ================ 
"r_particle_max_texture_layers" "2" // Установите 4-6 для удаления белых / блочных частиц
"r_particle_max_detail_level" "0"
"r_particle_cables_cast_shadows" "0"
"r_RainParticleDensity" "r_physics_particle_op_spawn_scale"
"r_physics_particle_op_spawn_scale" "0"
 r_particle_min_timestep" "0"
"r_particle_max_size_cull" "800"
"particle_cluster_nodraw" "1"
"r_particle_mixed_resolution_viewstart" "800"

// ================ PHYSICS & CLOTH ================
"cloth_update" "1"                   // Enable cloth physics
"cloth_sim_on_tick" "0"
"presettle_cloth_iterations" "3"
"pred_cloth_pos_max" "1.0"          // Reduce cloth prediction
"pred_cloth_pos_multiplier" "0.3"
"pred_cloth_pos_strength" "0.1"
"pred_cloth_rot_high" "0.05"
"pred_cloth_rot_low" "0.005"
"pred_cloth_rot_multiplier" "0.2"
"cl_phys_timescale" "0"             // Disable physics

// ================ MODEL & DECAL OPTIMIZATIONS ================
"r_drawmodeldecals" "0"
"r_character_decal_resolution" "1"
"r_decals" "16"                   // Number of Decals being drawn
"r_propsmaxdist" "800"
"props_break_max_pieces_perframe" "0"
"r_citadel_screenspace_particles_full_res" "0"
"r_citadel_gpu_culling_shadows" "1"
"skeleton_instance_lod_optimization" "1"
"r_size_cull_threshold" "1.2"
"r_hair_ao" "0"

// ================ ROPE PHYSICS ================
"rope_collide" "0"
"rope_subdiv" "0"
"rope_wind_dist" "0"
"rope_smooth_enlarge" "0"
"rope_smooth_maxalpha" "0"
"rope_smooth_maxalphawidth" "0"
"rope_smooth_minalpha" "0"
"rope_smooth_minwidth" "0"
"r_ropetranslucent" "0"

// ================ TERRAIN & FOLIAGE ================
"r_grass_quality" "0"
"r_grass_start_fade" "0"
"r_grass_end_fade" "0"

// ================ Пользовательский ИНТЕРФЕЙС И HUD ================ 
"panorama_disable_box_shadow" "1"
"r_dashboard_render_quality" "1"
"closecaption" "ложь"
"citadel_hud_objective_health_enabled" "1" // 0= Выключено, 1= Святилища, 2= T1 / T2, 3 = Казармы
"citadel_boss_glow_disabled" "1"
"citadel_damage_offscreen_indicator_disabled" "1"
"citadel_camera_fade_other_near_opacity" "0.4" // Установить 0.4, если hpbar не виден
«citadel_portrait_world_renderer_off» «истина»

// Текст повреждения (задайте его в соответствии с вашими предпочтениями)
"citadel_damage_text_lifetime" "1.5"
"citadel_damage_text_lifetime_new" "0.75" 
"citadel_damage_text_lifetime_accumulated_new" "2" // ================ СЕТЬ И ПРОГНОЗИРОВАНИЕ ================ 
"cl_prediction_savedata_postentitypacketreceived" "1"
"r_frame_sync_enable" "0" 

// ================ ОПТИМИЗАЦИЯ С ПОМОЩЬЮ искусственного ИНТЕЛЛЕКТА ================ 
"ai_strong_optimizations_no_checkstand" "1"
"ai_expression_optimization" "1" 

// ================ РАЗНОЕ ================ 
"sc_hdr_enabled_override" "0"
"качество r_texturefiltering" "0"
"cl_ragdoll_limit" "0"
"rtx_force_default_hitgroup" "1"
"citadel_show_new_damage_feedback_numbers" "0" // Устаревшая версия
